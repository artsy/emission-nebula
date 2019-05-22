# emission-nebula

Handles weekly deploys of Emission to TestFlight. 

* __State:__ production
* __Point People:__ [@ashfurrow](https://github.com/ashfurrow)
* __Builds:__ https://travis-ci.org/artsy/emission-nebula/builds

### Deploying manually

* Clone this repo: `git clone https://github.com/artsy/emission-nebula.git`
* `cd emission-nebula`
* Update fastlane with `bundle update`.
* Run `bundle exec fastlane setup` to setup a copy of Emission.
* Ensure your certs are up to date via `bundle exec fastlane match appstore --readonly`
* Run `bundle exec fastlane ship` .

### Updating certs

* `bundle exec fastlane match appstore`

## Docs

* [Deploying weekly with fastlane](http://artsy.github.io/blog/2017/07/31/fastlane-travis-weekly-deploys/)
* [What is match?](http://artsy.github.io/blog/2017/04/05/what-is-fastlane-match/)
* [Automating Testflight deploys with fastlane](http://artsy.github.io/blog/2015/12/14/Automating-Testflight-Deploys/)
