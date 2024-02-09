# Check-in

Check-in is an app for answering a few questions about yourself each day.

The app is written in astro, the forms are saved using netlify Forms. Notifications are supported via [ntfy.sh](ntfy.sh).

## Inspiration

This little project inspired by inspired by Blake Watson's [home-cooked apps](https://blakewatson.com/journal/magnoliajs-2023-the-joys-of-home-cooked-apps/).

## Dev Notes

## Architecture

1. Github action calls the nfty.sh API to send a notification.
2. The nfty.sh server receives the notification.
3. Nfty notifies the phone app, which is subscribed to the topic.
4. User clicks the notification, navigating them to the check-in website.
5. The user fill outs the form on the check-in website and submits.
6. The form is submitted to Netlify forms, which persists the data.

TODO: wipe git history
TODO: delete back up branch
TODO: make public with apache 2 license

### General Use

```bash
npm install
npm run dev
```

## Ntfy

- Home page: ntfy.sh/
- Docs: https://docs.ntfy.sh/
- Ntfy app: https://ntfy.sh/app

```
curl \
  -H "Title: Daily Check-in" \
  -H "Click: https://check-in-daily.netlify.app/" \
  -d "Click do to your daily check-in" \
  ntfy.sh/mytopic
```
