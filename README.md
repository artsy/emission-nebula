# emission-nebula

Handles weekly deploys of Emission to TestFlight

### Deploying manually

* Update Fastlane with `bundle update`.
* Run `bundle exec fastlane setup` to setup a copy of Emission.
* Open the Emission Xcode Project with `open emission/Example/Emission.xcworkspace`.
* Run "Archive" making sure the scheme is "Deploy" by holding alt when you "Archive".
* Once the archive has finished, open the xcarchive in finder (right click on it.)
* Copy the path of the xcarchive (`cmd + alt + c` in Finder.)
* Paste the path into the `gym` action inside `fastlane/Fastfile`, it should look like:

  ```ruby
    gym workspace: 'emission/Example/Emission.xcworkspace',
      configuration: 'Deploy',
      scheme: 'Emission',
      skip_build_archive: true,
      archive_path: '/Users/orta/Library/Developer/Xcode/Archives/2017-06-16/Emission 16-06-2017, 10.03.xcarchive'
  ```
  * Ensure you have all the ENV vars set up ( there's a validator with `bundle exec fastlane validate_env_vars`. )
  * Comment out `setup_signing` at the top of `lane :ship`.
  * Run `bundle exec fastlane ship`.
