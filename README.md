## Hi there 👋

<!--
**madhukazz/madhukazz** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
name: Update README

on:
  schedule:
    - cron: '0 0 * * *'
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: anuraghazra/github-readme-stats@master
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          username: your-username
      - uses: DenverCoder1/github-readme-streak-stats@master
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          username: your-username
      - run: |
          # Update README with new stats
          cat <<EOF >README.md
          # My GitHub Stats

          ![Contribution Graph](https://github-readme-stats.vercel.app/api?username=your-username&show_icons=true&theme=dark)
          ![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=your-username)

          ## Languages
          ![JavaScript](https://img.shields.io/badge/JavaScript-47.70%25-yellow)
          ![CSS](https://img.shields.io/badge/CSS-35.00%25-blue)
          ![HTML](https://img.shields.io/badge/HTML-15.22%25-red)
          ![Java](https://img.shields.io/badge/Java-1.91%25-orange)
          ![EJS](https://img.shields.io/badge/EJS-0.18%25-purple)

          ## Tools and Technologies
          ![JavaScript](path/to/javascript-logo.png)
          ![TypeScript](path/to/typescript-logo.png)
          ![CSS](path/to/css-logo.png)
          ![Java](path/to/java-logo.png)
          ![MySQL](path/to/mysql-logo.png)
          ![WordPress](path/to/wordpress-logo.png)
          ![MongoDB](path/to/mongodb-logo.png)
          ![React](path/to/react-logo.png)
          ![TailwindCSS](path/to/tailwindcss-logo.png)
          ![Material-UI](path/to/material-ui-logo.png)
          ![Node.js](path/to/nodejs-logo.png)
          ![Docker](path/to/docker-logo.png)
          ![Firebase](path/to/firebase-logo.png)
          ![Git](path/to/git-logo.png)
          ![GitHub](path/to/github-logo.png)
          ![NPM](path/to/npm-logo.png)
          ![Cat](path/to/cat-logo.png)
          EOF

      - name: Commit changes
        run: |
          git config --global user.name 'github-actions[bot]'
          git config --global user.email 'github-actions[bot]@users.noreply.github.com'
          git add .
          git commit -m 'Update README'
          git push
