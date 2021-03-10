

-  [Performance — Blender Manual](https://docs.blender.org/manual/en/latest/render/cycles/render_settings/performance.html?#performance)
	- ## Threads[](https://docs.blender.org/manual/en/latest/render/cycles/render_settings/performance.html?#threads "Permalink to this headline")
		- [电脑核数和线程数](https://blog.csdn.net/huazicomeon/article/details/53540852)
			- 方法1.命令行查看
				- 第一步：开始菜单->运行->cmd->输入 wmic->输入 cpu get *
				- 第二步：拖动底部滑动栏至下图所示位置
				- 第三步：NumberOfCores为核数 NumberOfLogicalProcessors为线程数，大家可以看到我的电脑实际为四核八线程。

			- 方法2.工具
				- Speccy（安装比较简单，在此不赘述），安装完成后，打开软件点击CUP即可看到CPU相关信息。

		- Mode
		- Auto-Detect

		- Automatically chooses the amount of threads to match the number of logical processors on your computer.

		- Fixed

			- Manually choose the maximum number threads to use for rendering. This can be useful for example, if you want to use your computer while rendering, you can set the property to a thread count lower the amount of logical processors on your computer.

		- Threads

		- The maximum number of CPU cores to use simultaneously while rendering.

	- ## Tiles[](https://docs.blender.org/manual/en/latest/render/cycles/render_settings/performance.html?#tiles "Permalink to this headline")

		- Tiles X, Y

			- The size of the tiles for rendering.

			- Depending on what device you are using for rendering, different tile sizes can give faster renders. For CPU rendering smaller tiles sizes (like 32 × 32) tend to be faster, while for [GPU rendering](https://docs.blender.org/manual/en/latest/render/cycles/gpu_rendering.html) larger tile sizes give a better performance (like 256 × 256).
		- Order

			- Order of rendering tiles. This does not significantly affect the performance.

			- Progressive Refine

		- Instead of rendering each tile until it has finished every sample, refine the whole image progressively. Note that progressive rendering is slightly slower than tiled rendering, but time can be saved by manually stopping the render when the noise level is low enough.

		- For rendering animations it is best to disable this feature, as stopping a frame early is not possible.

	- ## Acceleration Structure[](https://docs.blender.org/manual/en/latest/render/cycles/render_settings/performance.html?#acceleration-structure "Permalink to this headline")

		- Use Spatial Splits

		- Spatial splits improve the rendering performance in scenes with a mix of large and small polygons. The downsides are longer BVH build times and slightly increased memory usage.

		- Use Hair BVH

		- Use a special type of [BVH](https://docs.blender.org/manual/en/latest/glossary/index.html#term-BVH) for rendering hair. The bounding boxes are not axis aligned allowing a spatially closer fit to the hair geometry. Disabling this option will reduce memory, at the cost of increasing hair render time.

		- BVH Time Steps

		- Split BVH primitives by this number of time steps to speed up render time at the expense of memory.

	- ## Final Render[](https://docs.blender.org/manual/en/latest/render/cycles/render_settings/performance.html?#final-render "Permalink to this headline")

		- Save Buffers

			- Saves all render layers and passes to the temp directory on a drive, and reads them back after rendering has finished. This saves memory (RAM) usage during rendering, particularly when using many render layers and passes. This can be read back in the Compositor and Image editor by using [Layers](https://docs.blender.org/manual/en/latest/interface/controls/nodes/editing.html#bpy-ops-node-read-viewlayers).

		- Persistent Images

			- Keep image data in memory after rendering, for faster re-renders at the cost of extra memory usage when performing other tasks in Blender.

	- ## Viewport[](https://docs.blender.org/manual/en/latest/render/cycles/render_settings/performance.html?#viewport "Permalink to this headline")

		- Pixel Size

			- Option to control the resolution for viewport rendering. Allows you to speed up viewport rendering, which is especially useful for displays with high DPI.

		- Start Pixels

			- Resolution to start rendering preview at, progressively increase it to the full viewport size.

- Denoise
	-  2.81 and above
		[](https://blender.stackexchange.com/posts/211942/timeline)
		compositing, and enable nodes.
		search and enter denoising. drag the node:

		[![enter image description here](https://i.stack.imgur.com/aA6i4.png)](https://i.stack.imgur.com/aA6i4.png)

		If you are unable to find denoising normal and denoising albedo, you will find it here on the left:

		[![enter image description here](https://i.stack.imgur.com/CcGT2.png)](https://i.stack.imgur.com/CcGT2.png)	





