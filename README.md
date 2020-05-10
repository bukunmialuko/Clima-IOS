# Clima

## Description

Clima is a location-aware weather app. It will find out where you are in the world and query an open source weather service to retrieve the temperature and weather conditions. Also, you can change the city at the tap of a button. Want to know what it’s like in Lagos? Clima is here to help. 

<!-- ## External Libraries

* [Alamofire](https://cocoapods.org/pods/Alamofire) - Used for making HTTP requests
* [SVProgressHUD](https://cocoapods.org/pods/SVProgressHUD) -  For displaying the progress of an ongoing task 
* [SwiftyJSON](https://cocoapods.org/pods/SwiftyJSON) - Used for parsing Json -->

## Screenshots
<div align="center">
<img src="art/ScreenShot1.png" width="200px" />
<img src="art/ScreenShot2.png" width="200px" />
<img src="art/ScreenShot3.png" width="200px" />
</div>


## Fix for Cocoapods v1.0.1 and below

```ruby
post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['SWIFT_VERSION'] = '3.0'
      config.build_settings['MACOSX_DEPLOYMENT_TARGET'] = '10.10'
    end
  end
end
```

## Fix for App Transport Security Override

```XML
	<key>NSAppTransportSecurity</key>
	<dict>
		<key>NSExceptionDomains</key>
		<dict>
			<key>openweathermap.org</key>
			<dict>
				<key>NSIncludesSubdomains</key>
				<true/>
				<key>NSTemporaryExceptionAllowsInsecureHTTPLoads</key>
				<true/>
			</dict>
		</dict>
	</dict>
```

>This is a companion project to The App Brewery's Complete App Developement Bootcamp, check out the full course at [www.appbrewery.co](https://www.appbrewery.co/)

