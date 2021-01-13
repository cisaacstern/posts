This is inspired in part by Marc's [template](https://github.com/MarcSkovMadsen/awesome-analytics-apps-template) 
and also draws heavily on [this post from testdriven.io](https://testdriven.io/blog/dockerizing-flask-with-postgres-gunicorn-and-nginx/).

For starters, you should have a virtual environment activated with your dependenices. I prefer conda.

Now click "Use Template" and `git clone` the resulting repo to your local machine.

Your panel app should have an `app.py` in its root directory which contains a [servable panel app] which is itself named `servable`. 
For example, in my `app.py` I build up a [panel.template] called `react`, and then, at the end of `app.py`, assign `servable = react.servable()`. Perhaps your servable is not a template? It might be as simple as a single [panel.row], in which case at the end of your you would simply assign:

    my_row = pn.Row(<some models>)
    servable = my_row.servable()

The app root director should also contain a `requirements.txt` for dependencies. 

To swap in your panel app directory, first make sure you are in the root directory.
Then delete the example repo with `rm -r service/web/terrain-corrector` and also `rm .gitmodules` and `git deinit submodules`.

Then define `USERNAME=<your_github_username>` and `PANELAPP=<your_panel_app_repo_name>`.

Then run `git submodule init github.com/$USERNAME/$PANELAPP.git services/web/$PANELAPP`.

You cab now verify that your app works changing to the `services/web` directory and running `panel serve $REPONAME/app.py --show`.

Then update `services/web/settings/config.toml` accordingly:

    REPO_NAME =
    SITE_NAME =
    NUM_PROCS =
    WEBSOCKETS =

Now, from the web directory you can run `python 

