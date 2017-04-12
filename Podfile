target 'UnitTestPodDemo' do
	pod 'CDZPicker'
	pod 'UnitTestPod' , :path => 'UnitTestPod/UnitTestPod.podspec' ,:configurations => ['Test']
end

post_install do |installer|
	installer.pods_project.targets.each do |target|
		 if target.name == "UnitTestPod"
             target.product_type = 'com.apple.product-type.bundle.unit-test'
             target.build_configurations.each do |config|
             	config.build_settings['OTHER_LDFLAGS'] = '$(inherited)'
				config.build_settings['LIBRARY_SEARCH_PATHS'] = '$(inherited)'
             end
             puts "`#{target.name}` change type to `#{target.product_type}`"
         end
	end
end
