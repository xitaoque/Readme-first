
		至亲爱的读者:

		感谢你们的信任，选择购买我写的书籍。笔者才疏学浅，书中难免有各种不足之处，请大家海涵。如果发现了什么问题，欢迎
		在本GitHub中留言。笔者向出版社交稿的时候，书中的内容覆盖了RN 0.23.0版本的绝大部分特性。但到RN以平均每两周发布
		一个小版本升级的速度高速发展着。不可避免的，书中的某些语法在使用时，会看到警告声明它们被不建议被使用，或者是已
		经被废弃。笔者在本文中，将这些语法列出来，并列出替换它们的新语法。同时还会记录一些读者需要注意的事项。


		一、RN开发环境安装
		
    		在笔者向出版社交稿时，RN对Windows环境的支持还是不断的改进中，但现在RN已经正式宣布支持Windows开发环境，并且在官
    		方文档中列出了详细的安装步骤。与原来书中描述的步骤有许多不同。因些请读者阅读官方文档相应部分。它们的网址在这里
    		再列出一下，英文网址：http://facebook.github.io/react-native/docs/getting-started.html；书中还列出了一个中
    		文网址。但现在发现它的更新不及时。因此还是建议读者看英文网址中的英文内容。至少安装这部分仔细看一下，借助电脑的
    		翻译功能应当是问题不大的。
    		网上有很多安装RN环境的教程与经验，它们中的很多都是老版本的RN开发环境安装经验，请读者安装时以官方文档为准。其它
    		文档只能参考。
    		强烈建议读者在苹果操作系统下进行RN开发。如果你没有苹果电脑，但你的电脑有16G内存，80G空闲的SSD存储空间，请自行百
    		度“虚拟机 苹果系统”。


		二、新的导入React与其组件的语法

   		从RN0.29起，不再允许老的导入RN与RN组件的语法了。我的书中使用ES5语法编写的例程仍然是可以使用的，只是每个例程都需
   		要替换两个语句：
   		
    		第一句是：let React = require('react-native');在最新版本的RN开发中，把这个语句替换为：
    		import React, { Component } from 'react';

   		第二句类似于：
			let {
				AppRegistry, 
				StyleSheet, 
				Text, 
				View,
				TextInput
			} = React;
    		在新版本的RN开发中，保持这部分中大括号的内容不变，将它改为
			import {
				//大括号中的内容保持不变	
			} from 'react-native';
    
    		三、选择ES 5还是ES 6

   		有些读者不能确定学习时使用ES 5语法还是使用ES 6语法。有些读者认为ES 6语法比ES 5语法新一些。以我个人肤浅的理解，对于
   		真正的JavaScript开发，ES 6比ES 5肯定有一些先进的特性。但在RN开发中，暂时还没有使用到ES 6语法的那些先进的特性。RN代
   		码中的ES 5写法与ES 6写法都可以实现RN的各个功能，并且可以一一对应的转换。因此在RN开发中，不存在谁老谁新的问题。

   		我曾经考虑过是不是要用ES 6语法来写这本书。三个原因让我最终决定还是使用ES 5语法写这本书。
   		
			一、ES 5语法与ES 6语法是可以一一对应转换的，并且书中有章节描写如何对应转换；
    			
			二、太多项目的代码还是ES 5语法开发的（包括RN的官方文档中的例程），如果我用ES 6语法写这本书，读者入门后再看
	 		    ES 5代码会不习惯。但如果从ES 5代码学起，再学怎么改为ES 6代码，两种语法都能掌握。
	 		    
			三、使用ES 6语法编写React Native组件时，React Native组件的回调函数必须在组件的构造函数中执行绑定操作。这事
			    实上对开发者而言还多了一些工作。在商用的项目中，回调函数比较多，很容易忘记绑定某一个回调函数。一旦出现
			    这种错误，不容易查找出错误原因。

		四、Promise机制

   		本书中7.3节数据存储部分介绍数据存储功能时介绍每一个功能都有三种使用方法，分别是：没有操作完成后处理的方法，使用
   		回调函数进行操作完成后处理的方法与使用Promise机制进行操作完成后处理的方法。在最新版本的RN中，不能再使用“使用回调
   		函数进行操作完成后处理的方法”。事实上鼓励使用Promise机件是RN开发的一个方针，还有一些操作原来也提供了“使用回调函
   		数进行操作完成后处理的方法”与“使用Promise机制进行操作完成后处理的方法”。在新版本中，“使用回调函数进行操作完成后处
   		理的方法”也不再被支持或者即将被不支持。
   		从本质来讲，“使用回调函数进行操作完成后处理的方法”与“使用Promise机制进行操作完成后处理的方法”只是代码的写法上有些
   		不同，读者稍微注意一下就可以了。

		
    
		五、RN 0.29的最新变化
    		2016.7.7刚发布的RN 0.29，对初学者最大的变化是：使用iOS真机调试时，不需要修改Objective-C代码中的各个IP地址了。
    		本书2.2.5.1中原来针对真机调试写的章节做废了。直接插上手机就可以开始调试了。
    
