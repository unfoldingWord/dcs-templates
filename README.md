# dcs-templates
This is our custom templates to deploy on the server that overrides built-in DCS templates.

The original DCS template files are here: https://github.com/unfoldingWord/dcs/tree/main/templates
(to override a file, just copy in the file with the exact same path and file name)

The templates here are assumed to be what will work on whatever version of DCS (Gitea) being used on the produiciton server. 

QA and Develop might be running a different version, so the templates should be built into those nightly builds.

# Editing & Testing Your Own Template Changes

## Prerequisites
It is assumed that Docker is installed and running. If not, please [go here](https://www.docker.com/get-started/) and follow the instructions.
Make sure that Docker Compose [is installed](https://docs.docker.com/compose/install/) as well. This might be a separate step for your environment. 

The availability of [git](https://git-scm.com/download) is also needed. 

## Steps to run your own instance of DCS

1. Open up a terminal on your machine and clone this repo:

    ```
    git clone https://github.com/unfoldingWord/dcs-templates.git
    ```

2. Change to the repo directory you just created

    ```
    cd dcs-templates
    ```

3. Edit existing custom templates in the `templates/` directory or add new ones you wish to modify by downloading them from the https://github.com/unfoldingWord/dcs/tree/main/templates and giving them the same path and file name in the `templates/` directory.

4. Run docker compose:

    ```
    docker compose up
    ```

    Keep this running in the terminal

5. Go to http://localhost:3000 in your web browser and you should see the home page.

6. Go to the page you modified if not the home page. If you need to log in, register a user, or use the admin user that is already set up:

    **username:** root \
    **password:** password

7. In the terminal where you started docker, to see any new changes, especially to newly added template files, you may need to bring it down with `CTRL-C` (or `Command-C` on Mac) and start it up again with `docker compose up`.
