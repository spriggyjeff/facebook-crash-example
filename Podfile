
source 'https://github.com/CocoaPods/Specs'

platform :ios, '9.3'
workspace 'Facebook Crash Example.xcworkspace'

use_modular_headers!

def main_pods
  pod 'Bolts'
  pod 'FacebookCore'
  pod 'FBSDKCoreKit'
  pod 'FBSDKMarketingKit'

  pod 'RealmSwift'
end

abstract_target "main_pods" do
  main_pods

  target 'Facebook Crash Example' do
  end
end

def set_deployment_target(target, version='9.3')
  target.build_configurations.each do |config|
    config.build_settings['IOS_DEPLOYMENT_TARGET'] = version
    config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = version
  end
end

def set_swift_version(target, version='4.1')
  target.build_configurations.each do |config|
    config.build_settings['SWIFT_VERSION'] = version
  end
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    set_swift_version(target, '4.1')

    set_deployment_target(target)
  end
end

