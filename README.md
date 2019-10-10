# OpenSpecs

这里是tingke的私有库

执行下面👇的命令，在本地`~/.cocoapods/repos`目录下创建私有库
	
```
pod repo add OpenSpecs https://github.com/tingke/OpenSpecs.git
```

创建一个组件库

```
pod lib create CustomLib
```

向Spec Repo提交podspec

```
cd CustomLib

pod lib lint --allow-warnings

pod repo push OpenSpecs CustomLib.podspec --allow-warnings
```

在项目中使用

```
use_frameworks!

platform :ios, '10.0'

source 'https://github.com/CocoaPods/Specs.git'  # 官方库
source 'https://github.com/tingke/OpenSpecs.git' # 私有库

target 'DYDemo666' do
  pod 'DYDemoTools'
end
```