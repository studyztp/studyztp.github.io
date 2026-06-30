# Previewing locally & publishing

Before pushing changes live, it's worth running the site on your own machine so you can see exactly
how it will look. You have three options: a native Ruby/Jekyll install, Docker, or the VS Code
DevContainer. All serve the site at **<http://localhost:4000>**.

> **Live reload:** while the server runs, saving any content file auto-rebuilds and refreshes the
> page. The **one exception is `_config.yml`** — after editing it you must stop and restart the
> server.

---

## Option A — Native (Ruby + Jekyll)

### 1. Install Ruby, Bundler, and Node

On Linux / Windows Subsystem for Linux:

```bash
sudo apt install ruby-dev ruby-bundler nodejs
```

If you see `Unable to locate package ruby-bundler` / `… nodejs`, refresh your package lists first:

```bash
sudo apt update && sudo apt upgrade -y
```

…then re-run the install. On Linux you may also need build tools:

```bash
sudo apt install build-essential gcc make
```

On macOS:

```bash
brew install ruby
brew install node
gem install bundler
```

### 2. Install the site's Ruby dependencies

```bash
bundle install
```

- If you get errors, delete `Gemfile.lock` and run `bundle install` again.
- If you hit a **permissions** error (e.g. *"You don't have write permissions for the
  /var/lib/gems/… directory"* or *"…trying to write to /usr/local/bin"*), install the gems locally
  instead:

  ```bash
  bundle config set --local path 'vendor/bundle'
  bundle install
  ```

  On success you'll see new `vendor/` and `.bundle/` folders.

### 3. Serve the site

```bash
bundle exec jekyll serve -l -H localhost
```

Open <http://localhost:4000>. The server rebuilds and refreshes automatically as you edit.
(`bundle exec` ensures Jekyll uses this project's exact dependencies; plain `jekyll serve -l -H
localhost` also works if Jekyll is on your PATH.)

---

## Option B — Docker

No desire to install Ruby? With [Docker](https://www.docker.com/) installed, from the repo root:

```bash
chmod -R 777 .
docker compose up
```

Then open <http://localhost:4000>.

---

## Option C — VS Code DevContainer

If you use [VS Code](https://code.visualstudio.com/), this repo includes a
[DevContainer](https://code.visualstudio.com/docs/devcontainers/containers). VS Code usually offers
to reopen in the container automatically; if not, press **F1 → "Dev Containers: Reopen in
Container"**. It builds the environment and serves the site at <http://localhost:4000>, live-updating
as you edit.

---

## Publishing

There's no manual build/deploy step. Just commit and push to `master`:

```bash
git add -A
git commit -m "Describe your change"
git push
```

GitHub Pages rebuilds and publishes the live site (usually within a minute or two). You can watch
the build under the repository's **Settings → Pages** / **Actions** tab on GitHub.

### After pushing a talk

Adding or editing anything under `_talks/` triggers an automated job that geocodes talk locations
and pushes a follow-up commit (*"Automated update of talk locations"*). **Run `git pull` afterward**
so your local copy includes that bot commit before you make your next change. See
[talks.md](talks.md) for details.
