# DroidBinding_NELivePlayer
[网易视频云播放器SDK](http://vcloud.163.com/) com.netease.Neliveplayer 的Xamarin.Android绑定

遇到的困难及解决方法
-----------
问题：

Class Com.Netease.Neliveplayer.NEMediaPlayer has unknown base type com.netease.neliveplayer.a

解决方法：

```
<attr path="/api/package[@name='com.netease.neliveplayer']/class[@name='a']" name="obfuscated">false</attr>
```

解释：

Xamarin.Android在绑定时，会自动忽略混淆过的类型。混淆类的特征包括：
- 类名包含$符，例如：a$.class
- 类名全为小写字母，例如：a.class

上面的代码可以让xamarin生成“未混淆”的C#类型。

参见官方文档：[java-bindings-metadata#obfuscated](https://developer.xamarin.com/guides/android/advanced_topics/binding-a-java-library/customizing-bindings/java-bindings-metadata/#obfuscated)

感谢
-----------

在 刘敏 绑定的基础上完成的

License
-----------

```
Copyright 2016 wtffly

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```