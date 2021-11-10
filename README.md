# Eleventy Serverless "Cannot GET" Repro

**The problem:** I have a serverless template. Whenever I run `eleventy --serve`, this template works just fine. However, whenever I run `netlify dev`, I can't hit the serverless template. This seems to be impacting deploys to Netlify as well.

## Steps to reproduce

Clone and install dependencies:

```bash
git clone https://github.com/BenDMyers/eleventy-serverless-repro.git
cd eleventy-serverless-repro
npm install
```

Run `npm run dev` and head to <http://localhost:8080/dyn/?beep=boop>, and verify that the `<pre>` tag displays `boop`.

Run `netlify dev` and head to <http://localhost:8888/dyn/?beep=boop>, and I get `Cannot GET /.netlify/functions/onrequest/index.htm`.

## Research done

The serverless template seems to start breaking the moment I introduce any reference to `eleventy.serverless` into my template.