# Flowerpot on Vercel

This repository provides a simple index.php wrapper around a flowerpot
in a [garden](https://hmm.garden/). Any path requested from the domain
hosting the flowerpot will be shimmed to a request for the same path append
to the `FLOWERPOT_ROOT_URL` and replace the page.

## Steps to deploy on Vercel

To deploy this code in Vercel, take the following steps.

1. Fork this repository.
1. Modify the `XXXX` in the line `define('FLOWERPOT_ROOT_URL', 'XXXX')` in `api/index.php` to point to your garden.
1. Commit the change.
1. Import the forked repository in Vercel and [configure your custom domain](https://vercel.com/docs/custom-domains#).

See https://github.com/chckyn/notes-flowerpot for an example of a configured flowerpot running on Vercel.

## How does this work?

The `vercel.json` in your forked repository specifies that the [`vercel-php`](https://github.com/juicyfx/vercel-php)
runtime will run `api/index.php` on a serverless function on a Vercel edge
server. All page requests to your custom domain will route to `/api/index.php`.



