Hello! I’m [Andrew](https://github.com/adunkman), a programmer in the DC area. I somehow tricked everyone into believing that I’m a competent public speaker and programmer — it’s probably something to do with my skin color and gender, and that sucks.

I once saw a conference talk by [Kronda](https://twitter.com/kronda) which changed the way I thought about the privilege that I have — I had previously felt quite guilty about my situation, but she implanted the idea of leveraging my privileges to help correct the terribleness.

There’s a bit of a chicken-and-egg problem with conference speaking sometimes — not everyone wants to take a risk on someone new. I’ve found that after professional recordings of my previous talks were online, conferences were much more comfortable with selecting my talks — and those conferences were more likely to produce professional recordings. So how do you get your first recording online?

This is where I can help — I’m certainly not the most qualified, but I have a background in technical theater and the resources to give it a try. I could use your help, if you believe in what I am doing — open an issue and tell me your story.

Don’t believe in my mission? That’s okay, I’ll keep doing me. As my [favorite non-profit bar](https://www.yelp.com/biz/the-saloon-washington) says, “Life is good, ya-ya.”

# Development

To run this application locally, you’ll need to install the dependencies and then launch the web server which automatically recompiles the site when changes are made.

1. `gem install bundler`
2. `bundle install`
3. `bundle exec jekyll serve`

This will launch the site running locally at [http://localhost:4000](http://localhost:4000). Press <kbd>Ctrl</kbd>+<kbd>C</kbd> to stop the server.

# Deployment

This application is deployed automatically on merges to master via [Travis CI](https://travis-ci.org/adunkman/dctech.tv). The production build and deployment scripts are in [.travis.yml](.travis.yml).

# Production Environment

This web app is hosted as a [static application on Amazon S3](http://www.dctech.tv.s3-website-us-east-1.amazonaws.com/). The application is served at https://www.dctech.tv via [an Amazon CloudFront distribution](https://d2te2v7jo2hjiy.cloudfront.net).

The CloudFront distribution provides:

1. SSL from an Amazon-issued SSL certificate that was generated through Amazon Certificate Manager and is configured to auto-renew.
2. Custom security-related HTTP response headers through Amazon Lambda@Edge.

Lambda@Edge runs a Node.js function immediately before serving responses (`viewer-response` in Amazon’s language). The source of this code is unfortunately edited via Amazon’s interface and is therefore not in source control directly, however, an effort is made to keep all changes recorded in [lambda@edge.js](lambda@edge.js).

DNS for dctech.tv is provided by Amazon Route 53.

# Support and Presence

Support and promotion for dctech.tv is provided through [Twitter](https://twitter.com/dctechtv), [Facebook](https://www.facebook.com/dctechtv), [Instagram](https://www.instagram.com/dctech.tv), [YouTube](https://www.youtube.com/channel/UCm0-yrQg5iunLdpRKINWDwQ), and via email at support@dctech.tv.

Email for the dctech.tv domain is handled by https://mail.zoho.com/.

To ease the difficulties of replying to messages across these platforms, messages sent via Twitter, Facebook, and email are aggregated at https://dctechtv.freshdesk.com/.

# Credentials

Credentials for all services and accounts related to dctech.tv are stored in this repository in an encrypted 1Password vault. To unlock this vault, you’ll need to contact [@adunkman](https://github.com/adunkman) for him to grant the vault password to you.
