# Peliyagoda Concrete Plant Operations Dashboard

A static React app prototype for comparing the concrete production plan with actual operation and analyzing delivery delays.

## Publish with GitHub Pages

This repository includes a GitHub Actions workflow that builds the static app and publishes it to Pages whenever changes are pushed to `main`.

1. Create a GitHub repository. Keep it private if its source or any project information should not be public.
2. Upload the project files to the repository's `main` branch. Do not upload real plant records, exports, or backups.
3. In the repository, open **Settings → Pages** and choose **GitHub Actions** as the build and deployment source. The workflow uses `main` as its source branch.
4. Open the **Actions** tab and wait for **Deploy Peliyagoda Dashboard to GitHub Pages** to finish successfully.
5. Open the website URL shown in **Settings → Pages**.

The workflow builds only `@workspace/peliyagoda-dashboard` and publishes the static output. For a local build, run from the project root:

```sh
PORT=4173 BASE_PATH=/your-repository-name/ pnpm install --frozen-lockfile
PORT=4173 BASE_PATH=/your-repository-name/ pnpm --filter @workspace/peliyagoda-dashboard run build
```

For an owner or organization repository named `<owner>.github.io`, use `BASE_PATH=/` instead.

## Prototype data and security

Plans and actuals are saved in the current browser's local storage. They are not shared with other users or devices, and clearing that browser's site data removes them. The password gate runs in the browser and is not secure authentication. Use this only with demo or non-confidential data; a production system needs secure server-side authentication, an API, and a database.