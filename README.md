[![npm version](https://badge.fury.io/js/giveaway-grabber.svg)](https://badge.fury.io/js/giveaway-grabber)

# giveaway-grabber 🎁

This script will loop through all the [Amazon giveaways](https://www.amazon.com/ga/giveaways/) and try to submit entries for them. 

Wanted a reason to experiment with [Puppeteer](https://github.com/GoogleChrome/puppeteer), so here goes.

Note: does not support entries that require following someone.

## Installation

You can install giveaway-grabber using npm:

```bash
$ npm install -g giveaway-grabber
```

Or, you can clone this repo and run via `npm start`.

## Usage

As CLI:

```bash
$ gg --username=fake@example.com --password=123456
```

If cloned:

Copy .env.example to .env, adding your own Amazon username and password.

```bash
$ npm install
$ npm start
```

Note that the script will crash if the Chrome window is minimized! Check the console to monitor feedback.

If it does happen to die, re-start it on any page like:

```bash
$ gg --username=fake@example.com --password=123456 --page=34
```

OR

```bash
$ npm start -- --page=34
```

If you have two factor authentication enabled, add `--2FA` flag:

```bash
$ gg --username=fake@example.com --password=123456 --2FA
```

OR

```bash
$ npm start -- --2FA
```

The script will wait for you to enter your code. 

### CAPTCHAs

Every so often Amazon will present a CAPTCHA. The script will pause at this 
point and wait for you to enter it. The console will warn you with an `ENTER CAPTCHA` message.

If you would prefer it to just keep running, skipping any entries with captchas, add `IGNORE_CAPTCHAS` to the CLI or .env file:

```bash
$ gg --username=fake@example.com --password=123456 --IGNORE_CAPTCHAS
```
OR
```bash
AMAZON_USERNAME=fake@example.com
AMAZON_PASSWORD=123456
IGNORE_CAPTCHAS=1
```

## Questions

If you have any questions, just [open an issue](https://github.com/jpchip/giveaway-grabber/issues/new).

## Disclaimer

This project is not associated with Amazon in any way. I just created it for my own experimentation, so use at your own risk.
