<div align="center">
  <img height="152em" src="https://github-readme-stats.vercel.app/api?username=GabrielVCB&show_icons=true&theme=dark&include_all_commits=true&count_private=true"/>
  <img height="152em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=GabrielVCB&layout=compact&theme=dark&hide=html,css,scss" />
</div>

Languages
<p>
  <a>
    <img src="https://skillicons.dev/icons?i=java&theme=light" />
    <img src="https://skillicons.dev/icons?i=c,python" />
  </a>
</p>

name: Generate Datas

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"
  workflow_dispatch:

jobs:
  build:
    name: Jobs to update datas
    runs-on: ubuntu-latest
    steps:
      # Snake Animation
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: rafaballerini
          svg_out_path: dist/github-contribution-grid-snake.svg

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
  
