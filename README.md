# 👨‍💻 oliverlabs blog

[![](https://img.shields.io/github/actions/workflow/status/MrArkon/mrarkon.github.io/gh-pages.yml?logo=github&style=for-the-badge)](https://github.com/MrArkon/mrarkon.github.io/actions/workflows/gh-pages.yml)
[![](https://img.shields.io/github/license/MrArkon/mrarkon.github.io?style=for-the-badge)](https://github.com/MrArkon/mrarkon.github.io/blob/rewrite/LICENSE)
[![](https://img.shields.io/github/issues/MrArkon/mrarkon.github.io?label=ISSUES&logo=github&style=for-the-badge)](https://github.com/MrArkon/mrarkon.github.io/issues)

This repository hosts the source code for my personal blog. It is powered by [Hugo](https://gohugo.io/) and [PaperMod](https://git.io/hugopapermod). 

You can access the website at: https://oliverlabs.co.uk/.

## :book: Usage Instructions

Before proceeding please ensure you have installed [Hugo](https://gohugo.io/). You can use GitHub Codespaces or the devcontainer with Docker and VSCode to get started. 

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/oliverlabs/oliverlabs.github.io)

Requirements: 
- NodeJS (v20) 
- Hugo (v0.120.4)

Once setup, run the following commands from the root repository folder:

1. Update the PaperMod theme with the following command after cloning the repository:

   ```bash
   git submodule update --init --recursive
   ```
2. To run a development server use the following command:
  
   ```bash
   hugo server -D
   ```
   
   To build a static website run the following command:
   
   ```bash
   hugo build --minify
   ```

Website should be accessible from: [http://localhost:1313](http://localhost:1313/)

## :hammer_and_wrench: How To Use This Repo For Your Own Website

1. Fork this repo
1. Edit the `config.yml` file and enter your preferred parameters
1. Go to _"Settings > Pages"_, select _"GitHub Actions"_ for the _"Source"_ dropdown
1. Go to _"Actions"_, rerun the failed workflow
1. Your site should be available at `https://$USERNAME.github.io/`.


## :copyright: License
This project is licensed under the GPL-3.0 license. See the file [`LICENSE`](https://github.com/MrArkon/mrarkon.github.io/blob/master/LICENSE) for more information. 
If you plan to use any part of this source code in your website/portfolio, I would be really grateful if you include some form of credit somewhere. 

