This is inspired in part by Marc's [template](https://github.com/MarcSkovMadsen/awesome-analytics-apps-template) 
and also draws heavily on [this post from testdriven.io](https://testdriven.io/blog/dockerizing-flask-with-postgres-gunicorn-and-nginx/).

Click "Use Template" and `git clone` the resulting repo to your local machine.

Your panel app should have an `app.py` in its root directory which contains a [servable panel app], and should also contain a `requirements.txt` for dependencies.

To swap in your panel app directory, first make sure you are in the root directory.
Then delete the example repo with `rm -r service/web/terrain-corrector` and also `rm .gitmodules` and `git deinit submodules`.

Then define `USERNAME=<your_github_username>` and `PANELAPP=<your_panel_app_repo_name>`.

Then run `git submodule init github.com/$USERNAME/$PANELAPP.git services/web/$PANELAPP`.

Then in open `services/web/manage.py` and change the import path. 
### Note to self: change ^this^ so that `manage.py` runs off a `config.toml`, like Marc's site.
