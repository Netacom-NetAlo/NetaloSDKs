# Pods for NetaloCommonSDK
How to intergrate: 
#=================Init Podfile========================#
B1- Init Podfile
B2 -Add cmd in Podfile bellow:
#=================Add to Podfile=====================#

def rx_swift_pods
    pod 'RxSwift', '~> 6.2.0'
    pod 'RxCocoa', '~> 6.2.0'
    pod 'XCoordinator', '~> 2.0'
    pod 'RxGesture', '~> 4.0.2'
    pod 'RxRelay', '~> 6.2.0'
end

def database_pods
  pod 'RealmSwift', '10.12.0'
end

def language_pods
  pod 'RealmSwift', '10.12.0'
end

def netalo_pods
  pod 'NetaloSDKs', :git => 'http://gitlab.ecdc.vn/hieubui/NetaloSDKs', branch: 'demo/simulator_v1'
end

def common_pods
  pod 'MessageKit', :git => 'https://github.com/thanhphong-tran/messagekit'
  pod 'SwiftLinkPreview', :git => 'https://github.com/Netacom-NetAlo/SwiftLinkPreview', branch: 'dev_1.0'
  pod 'Kingfisher', '6.1.1'
  pod 'Carbon', '~> 1.0.0-rc.6'
  pod 'Localize-Swift', :git => 'http://gitlab.ecdc.vn/hieubui/nt-Localize-Swift'
  pod 'JitsiMeetSDK', git: 'https://github.com/Netacom-NetAlo/JitsiSDK-iOS.git', branch: 'dev_1.2'
  pod 'Socket.IO-Client-Swift', '14.0.0'
  pod 'ZIPFoundation', '~> 0.9'
end

def tracking_pods
  pod 'FBSDKCoreKit', '8.2.0'
  pod 'AppsFlyerFramework', '6.4.4'
  pod 'Sentry', :git => 'https://github.com/getsentry/sentry-cocoa.git', :tag => "4.3.1"
end

def secret_pods
  pod 'SignalCoreKit', git: 'https://github.com/signalapp/SignalCoreKit.git', :commit => 'eea6884e55261bf157ad6054c72c3c51d7788d4c'
  pod 'AxolotlKit', git: 'https://github.com/signalapp/SignalProtocolKit.git', branch: 'master'
  pod 'HKDFKit', git: 'https://github.com/signalapp/HKDFKit.git'
  pod 'Curve25519Kit', git: 'https://github.com/signalapp/Curve25519Kit'
  pod 'GRKOpenSSLFramework', git: 'https://github.com/signalapp/GRKOpenSSLFramework', branch: 'mkirk/1.0.2t'
end

def socket_pods
  pod 'Socket.IO-Client-Swift', '14.0.0'
end

def testing_pods
end

def resolver
  pod 'Resolver', tag: '1.4.4', git: 'https://github.com/thanhphong-tran/Resolver'
end

def component_pods
  resolver
  pod 'Carbon', '~> 1.0.0-rc.6'
  pod 'Kingfisher', '6.1.1'
end


def app_pods
  rx_swift_pods
  component_pods
  secret_pods
  database_pods
  netalo_pods
  language_pods
  tracking_pods
  common_pods
end

# ======================================TARGET PODS==========================================

target 'NetAlo' do
  app_pods
end

target 'NetAlo-Dev' do
  app_pods
end

target 'NetAloTests' do
  testing_pods
end

target 'NetAloUITests' do
  testing_pods
end
    
#===================================================#
