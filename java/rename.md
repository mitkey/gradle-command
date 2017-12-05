# 自动初始化 java 项目结构(模板)
	gradle init --type java-library
	
	生成以下目录结构 ---> []表示是文件夹，()表示是文件
		[].gradle 
		[]gradle
		[]src
		()build.gradle
		()gradlew
		()gradlew.bat
		()settings.gradle
		
# 常用任务
	若任务执行后面标识为 UP-TO-DATE，说明该任务被跳过了（上次执行后内容未改动，无效再次执行）

	gradle build
		编译并运行单元测试代码、打包 jar
		
	gradle clean
		删除所有编译输出的目录和文件
	
	gradle assemble
		编译并打包源码，不会允许单元测试
		
	gradle properties
		查看当前 gradle 构建的项目配置(可手动配置的)
		
# 常用 build.gradle 配置

	java 插件，可以使用提供的相关功能（tasks），如：编译源码、允许单元测试、打包 jar 文件等
	apply plugin: 'java'
	
	// TODO 在此处修改版本号
	version = 0.0.1
	// TODO 指定源码编译使用的 jdk
	sourceCompatibility = 1.8
	
	// TODO 依赖 jar 的来源仓库
	repositories {
		// .....
	}
	
	// TODO 依赖 jar
	dependencies {
		// .....
	}
	
	// TODO 对生成的 jar 配置启动该 jar 的 main 方法所在的入口类
	jar {
		manifest {
			attributes 'Main-Class':'main 方法所在的全类名'
		}
	}
	
	// TODO 源文件配置
	sourceSets{
		// TODO 逻辑相关
		main {
			// TODO 源码所在目录，默认是 src/main/java -- src/test/java
			java.srcDirs = ['src']
			// TODO 资源所在目录，默认是 src/main/resources -- src/test/resources
			resources.srcDirs = ['src']
		}
		// TODO 测试相关
		test {
			// ... 可配置项同 main
		}
	}
	
	// TODO 配置编译输出的文件夹，默认是 build
	buildDir = 'bin' 
	
	
	
	

		