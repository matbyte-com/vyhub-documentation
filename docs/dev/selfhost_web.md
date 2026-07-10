# Self-Hosted Frontend

On VyHub Self-Hosted, a custom frontend can be used. Self-hosting the frontend allows for 100% customizability of your
theme!
This allows you to customize the look and feel of
the frontend to match your brand or to add additional functionality.

The frontend is built with [Vue 3](https://vuejs.org/) and [Vuetify](https://vuetifyjs.com/) using [Vite](https://vitejs.dev/).

## Preparing the Frontend files

1. Clone the vyhub-web repository from GitHub:

   `git clone https://github.com/matbyte-com/vyhub-web.git`

2. Install [Node.js](https://nodejs.org/) (which includes `npm`) and run `npm install` in the cloned folder to install
   the required dependencies.

3. Copy `public/config.js.example` to `public/config.js` and adjust the values to match your VyHub instance:

    ``` js
    window.vyhubConfig = {
      backend_url: 'https://your-domain.com/v1', // API URL of your VyHub instance (including /v1)
      default_title: 'VyHub',                    // title shown in the browser tab
      demo_mode: false,                          // keep this false
    };
    ```

    > `public/config.js` is git-ignored, so your local changes will not be committed.

4. Run `npm run dev` to start the development server. You can open VyHub in your browser by navigating to
   `http://localhost:8050`.

5. Adjust the frontend code to your needs.

6. Run `npm run build` to build the frontend. The build files will be located in the `dist` folder.

    You can preview the production build locally with `npm run serve` (also served on `http://localhost:8050`).

## Deploying the Frontend

1. In `.env`, set `VYHUB_CUSTOM_FRONTEND` to `true`.

2. Recreate the containers with `docker compose up -d`.

3. Delete all files from the `web` folder (located in the directory where your `docker-compose.yml` is located).

4. Upload all files from the `dist` folder to the `web` folder.

5. Run `docker compose restart app`.
