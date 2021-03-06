LatexSlideGenerator
===================

用于自动创建LaTeX幻灯片所需要文件结构的脚本。只需要编辑一个json，脚本会根据json的内容，自动构建出一个LaTeX代码。
json格式：
```js
{
	"information" :
	{
		"title":"Slide Title",
		"author":"Yangff",
		"theme":"Warsaw",
		"entry":"sample",
		"usepackage":["amsmath"]
	}
	,

	"document":{
		"entry":"sample",
		"content":[
			{
				"title":"第一章",
				"entry":"topic1",
				"content":[
					{
						"title":"第一节",
						"entry":"section1",
						"content":[
							{"entry":"word1","title":"word1"},
							{"entry":"word2","title":"word2"},
							{"entry":"word3","title":"word3"}
						]
					}
					,
					{
						"title":"第二节",
						"entry":"section2",
						"content":[
							{"entry":"word1","title":"word1"},
							{"entry":"word2","title":"word2"},
							{"entry":"word3","title":"word3"}
						]
					}
				]
			},
			{
				"title":"第二章",
				"entry":"topic2",
				"content":[
					{
						"title":"第一节",
						"entry":"section1",
						"content":[
							{"entry":"word1","title":"word1"},
							{"entry":"word2","title":"word2"},
							{"entry":"word3","title":"word3"}
						]
					},
					{
						"title":"第二节",
						"entry":"section2",
						"content":[
							{"entry":"word1","title":"word1"},
							{"entry":"word2","title":"word2"},
							{"entry":"word3","title":"word3"}
						]
					}
				]
			}
		]
	}
}
```
会自动创建出如下的目录结构：
```
+./sample
+-./sample/topic1
+--./sample/topic1/section1
+---./sample/topic1/section1/word1.tex
+---./sample/topic1/section1/word2.tex
+---./sample/topic1/section1/word3.tex
+--./sample/topic1/section2
+---./sample/topic1/section2/word1.tex
+---./sample/topic1/section2/word2.tex
+---./sample/topic1/section2/word3.tex
+-./sample/topic2
+--./sample/topic2/section1
+---./sample/topic2/section1/word1.tex
+---./sample/topic2/section1/word2.tex
+---./sample/topic2/section1/word3.tex
+--./sample/topic2/section2
+---./sample/topic2/section2/word1.tex
+---./sample/topic2/section2/word2.tex
+---./sample/topic2/section2/word3.tex
```
使用的时候，使用命令`node xeslide sample.js`替换相关文件路径即可。

PS:npm包怎么做？
