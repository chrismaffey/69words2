# Static site

A tiny BusyBox HTTP server serves files from `public_html`.
Docker with the Compose plugin is required.

Start the server from the project root:

```sh
docker compose up -d
```

Open http://localhost:8080. Edit or add files in `public_html`; changes are
available immediately. Compose uses the BusyBox image directly; no Dockerfile
or image build is needed.

The page is a full-window text editor limited to 69 whitespace-separated words.
Text resizes to fit the window and saves automatically in the browser's local
storage, restoring on your next visit in the same browser. Pasting longer text
keeps the first 69 words.

Stop the server:

```sh
docker compose down
```

The server runs as an unprivileged user with a read-only document root and
container filesystem. Port 8080 is bound to the local machine only.
