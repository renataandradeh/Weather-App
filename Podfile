platform :ios, '11.0'
use_frameworks!

inhibit_all_warnings!

def testing_pods
    pod 'Quick', '1.3.1'
    pod 'Nimble', '7.1.3'
end

target 'Weather' do
    pod 'Moya', '11.0.2'
    pod 'SnapKit', '4.0.1'

    target 'WeatherTests' do
      inherit! :search_paths
      testing_pods
    end

    target 'WeatherUITests' do
      inherit! :search_paths
      testing_pods
    end
end

post_install do |installer|
    installer.pods_project.targets.each do |target|
        if target.name == 'SnapKit'
            target.build_configurations.each do |config|
                config.build_settings['SWIFT_VERSION'] = '4.2'
            end
        end
    end
end