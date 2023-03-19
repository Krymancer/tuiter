# Tuiter

![GitHub repo size](https://img.shields.io/github/repo-size/krymancer/tuiter?style=for-the-badge)
![GitHub language count](https://img.shields.io/github/languages/count/krymancer/tuiter?style=for-the-badge)
![GitHub forks](https://img.shields.io/github/forks/krymancer/tuiter?style=for-the-badge)
![Bitbucket open issues](https://img.shields.io/bitbucket/issues/krymancer/tuiter?style=for-the-badge)
![Bitbucket open pull requests](https://img.shields.io/bitbucket/pr-raw/krymancer/tuiter?style=for-the-badge)

![Logo](.github/assets/logo-400.png)

> Tuiter is a twitter clone made with rust and SolidJS

## 💻 Requirements

In order to build this project you need to meet some requirements:

- You need the most recent version of  [`rust`](https://www.rust-lang.org/) and [`node`](https://nodejs.org/)

- You read the documentation and readme of the frontend and backend project.

## ☕ Using

To run the project, make sure to run the backend and the frontend.

To run the backend, make sure you are in the backend sub-directory:

    cd backend
    cargo run --release

To run the frontend, also make sure to be in correct directory:

    cd frontend
    pnpm start # I use pnpm as a package manager, if you use npm, yarn, etc. Make sure to changeu


## 🔧 Building

You can build the two projects to deploy, for the backend, as is in rust:

    cd backend
    cargo build --release

This is create a binary in the target folder, that you can run. to more info in cross compiling to build and run in different platforms in rust check the [cookbook](https://rust-lang.github.io/rustup/cross-compilation.html)

To build the frontend project, as is a JavaScript framework:

    cd frontend
    pnpm build # Be sure to change pnpm to your package manager

This is transpile the code to the dist folder, that afterwards can be deployed to any web server.