# hastrumpfiredmuelleryet.com

A website which should always answer "no".

If it doesn't, [MoveOn](https://act.moveon.org/event/mueller-firing-rapid-response-events/search/).

## Cloudformation/Sceptre

Cloudformation for this site (using Sceptre) creates:

* a S3 bucket to store the static assets (`public_html/**/*`) and redirects for non-primary domains.
* DNS 
  * the hosted zone for `hastrumpfiredmuelleryet.com`
  * A records pointing `www.` and root to the S3 buckets
* a code pipeline which automatically updates the S3 bucket when we commit to Github.

```bash
export GITHUB_TOKEN=<secret!>
export AWS_PROFILE=sceptre
sceptre launch-env dev
```
