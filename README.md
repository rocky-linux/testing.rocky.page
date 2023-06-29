# Testing Team Wiki

This is the wiki repository for the Rocky Linux Testing Team.

https://testing.rocky.page

## Continuous Integration / Continuous Deployment

Actions Runner executes workflow to publish to https://testing.rocky.page on push to main.

## Local Development

To run a local instance of the wiki for development purposes, do the following:

    # Install dependencies
    pip3 install -r requirements.txt

    # Run the local mkdocs server
    mkdocs serve

The wiki will be available at http://127.0.0.1:8080 and will refresh automatically when edited files are saved.
