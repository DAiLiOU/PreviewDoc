## ResourcesAnalysis ##	
	[Create By Daili.Ou,Assist with HaiBing. 2023/12/15]
	
**** 项目静态资源分析 ****
* Mesh资源扫描
[1.统计Asset所有FBX重复Mesh]
[2.统计Mesh面数与顶点数Top100]
[3.统计Mesh带切线信息的网格]

* ParticleSystem资源扫描
[1.网格Read/Write]										// 规范 网格节点命名_RW	可开启
[2.网格面数是否超过 500]
[3.发射粒子最大数量超过 5]
[4.使用了非匹配列表的Shader]
[5.粒子贴图尺寸是否超过 256x256]
[6.命名不合法 包含"Particle System"]
[7.渲染器模式不是Mesh，资源冗余了网格引用]

* UI资源扫描
[1.可能九宫的UI资源扫描]
[2.引用了大图的UI预制体]
[3.使用了默认Text组件预制体(项目使用全量TMP)]
[4.使用了Tiled模式的Image组件]
[5.不可见的Image组件]
[6.不可见RawImage组件]
[7.使用了默认纹理的RawImage组件]
[8.使用了Outline组件的预制体]
[9.断舍离检测UI重复图片资源，并导出CSV]

* 材质资源扫描
[1.检测纯色图]											//泊松采样，快！准确率99%
[2.检测包含相同贴图采样]
[3.检测纹理采样数过多]
[4.空纹理采样检测] 										//没找到能获取空纹理的检测办法，修改了shaderGUI通过keyword控制来避免了空纹理采样

* Shader资源扫描
[1.可能生成变体数过多的shader]		< 100
[2.全局关键字过多的shader]			< 10

* 纹理资源扫描
[1.包含无效透明通道的纹理]
[2.开启各向异性过滤的纹理]
[3.尺寸过大的纹理]
[4.使用非ASTC格式的纹理]
[5.过滤模式为Trilinear的纹理]
[6.开启Read/Write选项的纹理]
[7.开启Mipmap选项的纹理]
[8.Wrap模式为Repeat的纹理(容易导致贴图边缘出现杂色)

// to add...
## ResourcesProcess ##

