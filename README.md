# Words and Personalities

This repo contains the [website](https://mismayil.github.io/words-personalities) code for Madry team's final ADA [project](https://github.com/epfl-ada/ada-2021-project-madry).

## Setup
This website is built using `jekyll` and hosted in Github Pages. CI is set up using Github actions which builds and deploys the final website to `gh-pages` branch upon commit push to the repo.

In order to run the website locally, please follow these setup instructions:
1. Install `ruby` ([Installing ruby](https://www.ruby-lang.org/en/documentation/installation/))
2. Install `bundle` and `jekyll` using `gem`.
```sh
gem install bundle jekyll
```
3. Clone this repo and install dependencies:
```sh
git clone git@github.com:mismayil/words-personalities.git
cd words-personalities
bundle install
```
4. Run the website locally (This command will rebuild the website every time you make a change)
```sh
bundle exec jekyll serve
```

Built on top of <a href="https://github.com/adueck/good-clean-read">Good Clean Read</a>.
