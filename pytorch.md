<h1>什么是 PyTorch?</h1>
PyTorch 是一个基于 Python 的科学计算包，主要定位两类人群：
<ul>
 	<li>NumPy 的替代品，可以利用 GPU 的性能进行计算。</li>
 	<li>深度学习研究平台拥有足够的灵活性和速度</li>
</ul>
<div id="getting-started" class="section">
<h2>开始学习</h2>
<div id="tensors" class="section">
<h3>Tensors (张量)</h3>
Tensors 类似于 NumPy 的 ndarrays ，同时  Tensors 可以使用 GPU 进行计算。
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="kn">from</span> <span class="nn">__future__</span> <span class="kn">import</span> <span class="n">print_function</span>
<span class="kn">import</span> <span class="nn">torch</span></pre>
</div>
</div>
</div>
</div>
构造一个5x3矩阵，不初始化。
<div id="getting-started" class="section">
<div id="tensors" class="section">
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="n">x</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">empty</span><span class="p">(</span><span class="mi">5</span><span class="p">,</span> <span class="mi">3</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="p">)</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">输出:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">tensor</span><span class="p">(</span><span class="mf">1.00000e-04</span> <span class="o">*</span>
       <span class="p">[[</span><span class="o">-</span><span class="mf">0.0000</span><span class="p">,</span>  <span class="mf">0.0000</span><span class="p">,</span>  <span class="mf">1.5135</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">0.0000</span><span class="p">,</span>  <span class="mf">0.0000</span><span class="p">,</span>  <span class="mf">0.0000</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">0.0000</span><span class="p">,</span>  <span class="mf">0.0000</span><span class="p">,</span>  <span class="mf">0.0000</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">0.0000</span><span class="p">,</span>  <span class="mf">0.0000</span><span class="p">,</span>  <span class="mf">0.0000</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">0.0000</span><span class="p">,</span>  <span class="mf">0.0000</span><span class="p">,</span>  <span class="mf">0.0000</span><span class="p">]])</span></pre>
</div>
</div>
&nbsp;

构造一个随机初始化的矩阵：
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="n">x</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">rand</span><span class="p">(</span><span class="mi">5</span><span class="p">,</span> <span class="mi">3</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="p">)</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">输出:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">tensor</span><span class="p">([[</span> <span class="mf">0.6291</span><span class="p">,</span>  <span class="mf">0.2581</span><span class="p">,</span>  <span class="mf">0.6414</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">0.9739</span><span class="p">,</span>  <span class="mf">0.8243</span><span class="p">,</span>  <span class="mf">0.2276</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">0.4184</span><span class="p">,</span>  <span class="mf">0.1815</span><span class="p">,</span>  <span class="mf">0.5131</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">0.5533</span><span class="p">,</span>  <span class="mf">0.5440</span><span class="p">,</span>  <span class="mf">0.0718</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">0.2908</span><span class="p">,</span>  <span class="mf">0.1850</span><span class="p">,</span>  <span class="mf">0.5297</span><span class="p">]])</span></pre>
</div>
</div>
&nbsp;

构造一个矩阵全为 0，而且数据类型是 long.

Construct a matrix filled zeros and of dtype long:
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="n">x</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">zeros</span><span class="p">(</span><span class="mi">5</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="n">torch</span><span class="o">.</span><span class="n">long</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="p">)</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">输出:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">tensor</span><span class="p">([[</span> <span class="mi">0</span><span class="p">,</span>  <span class="mi">0</span><span class="p">,</span>  <span class="mi">0</span><span class="p">],</span>
        <span class="p">[</span> <span class="mi">0</span><span class="p">,</span>  <span class="mi">0</span><span class="p">,</span>  <span class="mi">0</span><span class="p">],</span>
        <span class="p">[</span> <span class="mi">0</span><span class="p">,</span>  <span class="mi">0</span><span class="p">,</span>  <span class="mi">0</span><span class="p">],</span>
        <span class="p">[</span> <span class="mi">0</span><span class="p">,</span>  <span class="mi">0</span><span class="p">,</span>  <span class="mi">0</span><span class="p">],</span>
        <span class="p">[</span> <span class="mi">0</span><span class="p">,</span>  <span class="mi">0</span><span class="p">,</span>  <span class="mi">0</span><span class="p">]])</span></pre>
</div>
</div>
构造一个张量，直接使用数据：
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="n">x</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">tensor</span><span class="p">([</span><span class="mf">5.5</span><span class="p">,</span> <span class="mi">3</span><span class="p">])</span>
<span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="p">)</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">输出:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">tensor</span><span class="p">([</span> <span class="mf">5.5000</span><span class="p">,</span>  <span class="mf">3.0000</span><span class="p">])</span></pre>
</div>
</div>
创建一个 tensor 基于已经存在的 tensor。**用处????**
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="n">x</span> <span class="o">=</span> <span class="n">x</span><span class="o">.</span><span class="n">new_ones</span><span class="p">(</span><span class="mi">5</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="n">torch</span><span class="o">.</span><span class="n">double</span><span class="p">)</span>      
<span class="c1"># new_* methods take in sizes</span>
<span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>
<span class="n">x</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">randn_like</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">dtype</span><span class="o">=</span><span class="n">torch</span><span class="o">.</span><span class="n">float</span><span class="p">)</span>    
<span class="c1"># override dtype!</span>
<span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>                                      
<span class="c1"># result has the same size</span></pre>

<p class="sphx-glr-script-out">输出:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">tensor</span><span class="p">([[</span> <span class="mf">1.</span><span class="p">,</span>  <span class="mf">1.</span><span class="p">,</span>  <span class="mf">1.</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">1.</span><span class="p">,</span>  <span class="mf">1.</span><span class="p">,</span>  <span class="mf">1.</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">1.</span><span class="p">,</span>  <span class="mf">1.</span><span class="p">,</span>  <span class="mf">1.</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">1.</span><span class="p">,</span>  <span class="mf">1.</span><span class="p">,</span>  <span class="mf">1.</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">1.</span><span class="p">,</span>  <span class="mf">1.</span><span class="p">,</span>  <span class="mf">1.</span><span class="p">]],</span> <span class="n">dtype</span><span class="o">=</span><span class="n">torch</span><span class="o">.</span><span class="n">float64</span><span class="p">)</span>
<span class="n">tensor</span><span class="p">([[</span><span class="o">-</span><span class="mf">0.2183</span><span class="p">,</span>  <span class="mf">0.4477</span><span class="p">,</span> <span class="o">-</span><span class="mf">0.4053</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">1.7353</span><span class="p">,</span> <span class="o">-</span><span class="mf">0.0048</span><span class="p">,</span>  <span class="mf">1.2177</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">1.1111</span><span class="p">,</span>  <span class="mf">1.0878</span><span class="p">,</span>  <span class="mf">0.9722</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">0.7771</span><span class="p">,</span> <span class="o">-</span><span class="mf">0.2174</span><span class="p">,</span>  <span class="mf">0.0412</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">2.1750</span><span class="p">,</span>  <span class="mf">1.3609</span><span class="p">,</span> <span class="o">-</span><span class="mf">0.3322</span><span class="p">]])</span></pre>
</div>
</div>
获取它的维度信息:
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">size</span><span class="p">())</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">输出:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">torch</span><span class="o">.</span><span class="n">Size</span><span class="p">([</span><span class="mi">5</span><span class="p">,</span> <span class="mi">3</span><span class="p">])</span></pre>
</div>
</div>
<div class="admonition note">
<p class="first admonition-title">注意</p>
<p class="last"><code class="docutils literal notranslate"><span class="pre">torch.Size</span></code>  是一个元组，所以它支持左右的元组操作。</p>
<p class="last"></p>
<div id="operations" class="section">
<h3>操作</h3>
在接下来的例子中，我们将会看到加法操作。

加法: 方式 1
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="n">y</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">rand</span><span class="p">(</span><span class="mi">5</span><span class="p">,</span> <span class="mi">3</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">x</span> <span class="o">+</span> <span class="n">y</span><span class="p">)</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">Out:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">tensor</span><span class="p">([[</span><span class="o">-</span><span class="mf">0.1859</span><span class="p">,</span>  <span class="mf">1.3970</span><span class="p">,</span>  <span class="mf">0.5236</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">2.3854</span><span class="p">,</span>  <span class="mf">0.0707</span><span class="p">,</span>  <span class="mf">2.1970</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">0.3587</span><span class="p">,</span>  <span class="mf">1.2359</span><span class="p">,</span>  <span class="mf">1.8951</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">0.1189</span><span class="p">,</span> <span class="o">-</span><span class="mf">0.1376</span><span class="p">,</span>  <span class="mf">0.4647</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">1.8968</span><span class="p">,</span>  <span class="mf">2.0164</span><span class="p">,</span>  <span class="mf">0.1092</span><span class="p">]])</span></pre>
</div>
</div>
加法: 方式2
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="k">print</span><span class="p">(</span><span class="n">torch</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">y</span><span class="p">))</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">Out:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">tensor</span><span class="p">([[</span><span class="o">-</span><span class="mf">0.1859</span><span class="p">,</span>  <span class="mf">1.3970</span><span class="p">,</span>  <span class="mf">0.5236</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">2.3854</span><span class="p">,</span>  <span class="mf">0.0707</span><span class="p">,</span>  <span class="mf">2.1970</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">0.3587</span><span class="p">,</span>  <span class="mf">1.2359</span><span class="p">,</span>  <span class="mf">1.8951</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">0.1189</span><span class="p">,</span> <span class="o">-</span><span class="mf">0.1376</span><span class="p">,</span>  <span class="mf">0.4647</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">1.8968</span><span class="p">,</span>  <span class="mf">2.0164</span><span class="p">,</span>  <span class="mf">0.1092</span><span class="p">]])</span></pre>
</div>
</div>
加法: 提供一个输出 tensor 作为参数
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="n">result</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">empty</span><span class="p">(</span><span class="mi">5</span><span class="p">,</span> <span class="mi">3</span><span class="p">)</span>
<span class="n">torch</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="n">x</span><span class="p">,</span> <span class="n">y</span><span class="p">,</span> <span class="n">out</span><span class="o">=</span><span class="n">result</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">result</span><span class="p">)</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">Out:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">tensor</span><span class="p">([[</span><span class="o">-</span><span class="mf">0.1859</span><span class="p">,</span>  <span class="mf">1.3970</span><span class="p">,</span>  <span class="mf">0.5236</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">2.3854</span><span class="p">,</span>  <span class="mf">0.0707</span><span class="p">,</span>  <span class="mf">2.1970</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">0.3587</span><span class="p">,</span>  <span class="mf">1.2359</span><span class="p">,</span>  <span class="mf">1.8951</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">0.1189</span><span class="p">,</span> <span class="o">-</span><span class="mf">0.1376</span><span class="p">,</span>  <span class="mf">0.4647</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">1.8968</span><span class="p">,</span>  <span class="mf">2.0164</span><span class="p">,</span>  <span class="mf">0.1092</span><span class="p">]])</span></pre>
</div>
</div>
加法: in-place
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="c1"># adds x to y</span>
<span class="n">y</span><span class="o">.</span><span class="n">add_</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">y</span><span class="p">)</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">Out:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">tensor</span><span class="p">([[</span><span class="o">-</span><span class="mf">0.1859</span><span class="p">,</span>  <span class="mf">1.3970</span><span class="p">,</span>  <span class="mf">0.5236</span><span class="p">],</span>
        <span class="p">[</span> <span class="mf">2.3854</span><span class="p">,</span>  <span class="mf">0.0707</span><span class="p">,</span>  <span class="mf">2.1970</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">0.3587</span><span class="p">,</span>  <span class="mf">1.2359</span><span class="p">,</span>  <span class="mf">1.8951</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">0.1189</span><span class="p">,</span> <span class="o">-</span><span class="mf">0.1376</span><span class="p">,</span>  <span class="mf">0.4647</span><span class="p">],</span>
        <span class="p">[</span><span class="o">-</span><span class="mf">1.8968</span><span class="p">,</span>  <span class="mf">2.0164</span><span class="p">,</span>  <span class="mf">0.1092</span><span class="p">]])</span></pre>
</div>
</div>
<div class="admonition note">
<p class="first admonition-title">Note</p>
注意

任何使张量会发生变化的操作都有一个前缀 **'_'**。例如：**x.copy_(y)**, <code class="docutils literal notranslate"><span class="pre">x.t_()</span></code>, 将会改变 <code class="docutils literal notranslate"><span class="pre">x</span></code>.
<p class="last">你可以使用标准的  NumPy 类似的索引操作</p>

<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="p">[:,</span> <span class="mi">1</span><span class="p">])</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">Out:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">tensor</span><span class="p">([</span> <span class="mf">0.4477</span><span class="p">,</span> <span class="o">-</span><span class="mf">0.0048</span><span class="p">,</span>  <span class="mf">1.0878</span><span class="p">,</span> <span class="o">-</span><span class="mf">0.2174</span><span class="p">,</span>  <span class="mf">1.3609</span><span class="p">])</span></pre>
</div>
</div>
改变大小：如果你想改变一个 tensor 的大小或者形状，你可以使用 <code class="docutils literal notranslate"><span class="pre">torch.view</span></code>:

**！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！**

<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="n">x</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">randn</span><span class="p">(</span><span class="mi">4</span><span class="p">,</span> <span class="mi">4</span><span class="p">)</span>
<span class="n">y</span> <span class="o">=</span> <span class="n">x</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="mi">16</span><span class="p">)</span>
<span class="n">z</span> <span class="o">=</span> <span class="n">x</span><span class="o">.</span><span class="n">view</span><span class="p">(</span><span class="o">-</span><span class="mi">1</span><span class="p">,</span> <span class="mi">8</span><span class="p">)</span>  <span class="c1"># the size -1 is inferred from other dimensions</span>
<span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">size</span><span class="p">(),</span> <span class="n">y</span><span class="o">.</span><span class="n">size</span><span class="p">(),</span> <span class="n">z</span><span class="o">.</span><span class="n">size</span><span class="p">())</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">Out:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">torch</span><span class="o">.</span><span class="n">Size</span><span class="p">([</span><span class="mi">4</span><span class="p">,</span> <span class="mi">4</span><span class="p">])</span> <span class="n">torch</span><span class="o">.</span><span class="n">Size</span><span class="p">([</span><span class="mi">16</span><span class="p">])</span> <span class="n">torch</span><span class="o">.</span><span class="n">Size</span><span class="p">([</span><span class="mi">2</span><span class="p">,</span> <span class="mi">8</span><span class="p">])</span></pre>
</div>
</div>
如果你有一个元素 tensor ，使用 **.item()** 来获得这个 value 。（**通过下标定位到最终的值有`[]`，使用`item()`提取**）
<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="n">x</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">randn</span><span class="p">(</span><span class="mi">1</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">item</span><span class="p">())</span></pre>
</div>
</div>
<p class="sphx-glr-script-out">Out:</p>

<div class="sphx-glr-script-out highlight-default notranslate">
<div class="highlight">
<pre><span class="n">tensor</span><span class="p">([</span> <span class="mf">0.9422</span><span class="p">])</span>
<span class="mf">0.9422121644020081</span></pre>
</div>
</div>

# 自动微分

```python
import torch as th
x = th.randn(4,5)
x.requires_grad # 默认False
x.requires_grad_(True)
res = (x**2).sum() # 这种梯度只可以对标量使用
res.backward() # 反向传播，传播后才可以获取tensor的grad
print(x.grad) # 打印x的grad
```

autograd 包是 PyTorch 中所有神经网络的核心。首先让我们简要地介绍它，然后我们将会去训练我们的第一个神经网络。**该 autograd 软件包为 Tensors 上的所有操作提供自动微分**。它是一个由运行定义的框架，这意味着以代码运行方式定义你的反向传播，并且每次迭代都可以不同。我们从 tensor 和 gradients 来举一些例子。

1、TENSOR

torch.Tensor 是包的核心类。如果将其属性 **.requires_grad 设置为 True**，则会开始跟踪针对 tensor 的所有操作。完成计算后，您可以调用 .backward() 来自动计算**所有梯度**。该张量的梯度将累积到 **.grad 属性**中。

要停止 tensor 历史记录的跟踪，您可以调用 `.detach()??????`，它将其与计算历史记录分离，并防止将来的计算被跟踪。

要停止跟踪历史记录（和使用内存），您还可以将代码块使用 `with torch.no_grad():` 包装起来。在**评估模型**时，这是特别有用，因为模型在训练阶段具有 requires_grad = True 的可训练参数有利于调参，但在评估阶段我们不需要梯度。

还有一个类对于 autograd 实现非常重要那就是 Function。Tensor 和 Function 互相连接并构建一个非循环图，它保存整个完整的计算过程的历史信息。每个张量都有一个 .grad_fn 属性保存着创建了张量的 Function 的引用，（如果用户自己创建张量，则g rad_fn 是 None ）。

如果你想计算导数，你可以调用 Tensor.backward()。如果 Tensor 是标量（即它包含一个元素数据），则不需要指定任何参数backward()，但是如果它有更多元素，则需要指定一个gradient 参数来指定张量的形状。

<pre>import torch</pre>

创建一个张量，设置 requires_grad=True 来跟踪与它相关的计算

<pre><span class="n">x</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">ones</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">,</span> <span class="n">requires_grad</span><span class="o">=</span><span class="bp">True</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="p">)</span></pre>

输出：

<pre>tensor([[1., 1.],
        [1., 1.]], requires_grad=True)</pre>

针对张量做一个操作

<pre><span class="n">y</span> <span class="o">=</span> <span class="n">x</span> <span class="o">+</span> <span class="mi">2</span>
<span class="k">print</span><span class="p">(</span><span class="n">y</span><span class="p">)</span></pre>

输出：

<div class="sphx-glr-script-out highlight-none notranslate">
<div class="highlight">
<pre>tensor([[3., 3.],
        [3., 3.]], grad_fn=&lt;AddBackward0&gt;)
</pre>
</div>
</div>

y 作为操作的结果被创建，所以它有 grad_fn

<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="k">print</span><span class="p">(</span><span class="n">y</span><span class="o">.</span><span class="n">grad_fn</span><span class="p">)</span></pre>
</div>
</div>

输出：

<div class="sphx-glr-script-out highlight-none notranslate">
<div class="highlight">
<pre>&lt;AddBackward0 object at 0x7fe1db427470&gt;
</pre>
</div>
</div>

针对 y 做更多的操作：

<pre><span class="n">z</span> <span class="o">=</span> <span class="n">y</span> <span class="o">*</span> <span class="n">y</span> <span class="o">*</span> <span class="mi">3</span>
<span class="n">out</span> <span class="o">=</span> <span class="n">z</span><span class="o">.</span><span class="n">mean</span><span class="p">()</span>


<span class="k">print</span><span class="p">(</span><span class="n">z</span><span class="p">,</span> <span class="n">out</span><span class="p">)</span></pre>
输出：

<pre>tensor([[27., 27.],
        [27., 27.]], grad_fn=&lt;MulBackward0&gt;) tensor(27., grad_fn=&lt;MeanBackward0&gt;)</pre>

<code class="docutils literal notranslate"><span class="pre">.requires_grad_(</span> <span class="pre">...</span> <span class="pre">)</span></code> 会改变张量的 <code class="docutils literal notranslate"><span class="pre">requires_grad</span></code> 标记。输入的标记默认为  <code class="docutils literal notranslate"><span class="pre">False</span></code> ，如果没有提供相应的参数。

<pre><span class="n">a</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">randn</span><span class="p">(</span><span class="mi">2</span><span class="p">,</span> <span class="mi">2</span><span class="p">)</span>
<span class="n">a</span> <span class="o">=</span> <span class="p">((</span><span class="n">a</span> <span class="o">*</span> <span class="mi">3</span><span class="p">)</span> <span class="o">/</span> <span class="p">(</span><span class="n">a</span> <span class="o">-</span> <span class="mi">1</span><span class="p">))</span>
<span class="k">print</span><span class="p">(</span><span class="n">a</span><span class="o">.</span><span class="n">requires_grad</span><span class="p">)</span>
<span class="n">a</span><span class="o">.</span><span class="n">requires_grad_</span><span class="p">(</span><span class="bp">True</span><span class="p">)</span>
<span class="k">print</span><span class="p">(</span><span class="n">a</span><span class="o">.</span><span class="n">requires_grad</span><span class="p">)</span>
<span class="n">b</span> <span class="o">=</span> <span class="p">(</span><span class="n">a</span> <span class="o">*</span> <span class="n">a</span><span class="p">)</span><span class="o">.</span><span class="n">sum</span><span class="p">()</span>
<span class="k">print</span><span class="p">(</span><span class="n">b</span><span class="o">.</span><span class="n">grad_fn</span><span class="p">)</span></pre>

输出：

<pre>False
True
&lt;SumBackward0 object at 0x7fe1db427dd8&gt;</pre>

梯度：

我们现在后向传播，因为输出包含了一个标量，<code class="docutils literal notranslate"><span class="pre">out.backward()</span></code> 等同于<code class="docutils literal notranslate"><span class="pre">out.backward(torch.tensor(1.))</span></code>。

<div class="highlight-python notranslate">
<div class="highlight">
<pre><span class="n">out</span><span class="o">.</span><span class="n">backward</span><span class="p">()</span></pre>
</div>
</div>

打印梯度  d(out)/dx

<pre><span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">grad</span><span class="p">)</span></pre>
<div class="highlight-python notranslate">
<div class="highlight"> 输出：</div>
<div>
<div class="sphx-glr-script-out highlight-none notranslate">
<div class="highlight">
<pre>tensor([[4.5000, 4.5000],
        [4.5000, 4.5000]])</pre>
</div>
</div>
</div>
</div>

&nbsp;

原理解释：

<img class="alignnone size-full wp-image-106" src="http://pytorchchina.com/wp-content/uploads/2018/12/WechatIMG1376.jpeg" alt="" width="3544" height="1952" style="zoom: 25%;" />

<div class="trans-left">
<div class="trans-input-wrap">
<div class="input-wrap" dir="ltr">
<div class="input-operate">
<div class="op-favor-container"></div>
</div>
</div>
</div>
</div>
<div class="trans-right">
<div class="output-wrap small-font">
<div class="output-mod ordinary-wrap">
<div class="output-bd" dir="ltr">
<p class="ordinary-output target-output clearfix"><span class="">现在让我们看一个雅可比向量积的例子：</span></p>

<div class="highlight-python notranslate">
<div class="highlight"></div>
</div>
<pre><span class="n">x</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">randn</span><span class="p">(</span><span class="mi">3</span><span class="p">,</span> <span class="n">requires_grad</span><span class="o">=</span><span class="bp">True</span><span class="p">)</span>


<span class="n">y</span> <span class="o">=</span> <span class="n">x</span> <span class="o">*</span> <span class="mi">2</span>
<span class="k">while</span> <span class="n">y</span><span class="o">.</span><span class="n">data</span><span class="o">.</span><span class="n">norm</span><span class="p">()</span> <span class="o">&lt;</span> <span class="mi">1000</span><span class="p">:</span>
    <span class="n">y</span> <span class="o">=</span> <span class="n">y</span> <span class="o">*</span> <span class="mi">2</span>

<span class="k">print</span><span class="p">(</span><span class="n">y</span><span class="p">)</span></pre>
输出：

<div class="sphx-glr-script-out highlight-none notranslate">
<div class="highlight">
<pre>tensor([ -444.6791,   762.9810, -1690.0941], grad_fn=&lt;MulBackward0&gt;)</pre>
</div>
</div>

&nbsp;

现在在这种情况下，y 不再是一个标量。torch.autograd 不能够直接计算整个雅可比，但是如果我们只想要雅可比向量积，只需要简单的传递向量给 backward 作为参数。

<pre><span class="n">v</span> <span class="o">=</span> <span class="n">torch</span><span class="o">.</span><span class="n">tensor</span><span class="p">([</span><span class="mf">0.1</span><span class="p">,</span> <span class="mf">1.0</span><span class="p">,</span> <span class="mf">0.0001</span><span class="p">],</span> <span class="n">dtype</span><span class="o">=</span><span class="n">torch</span><span class="o">.</span><span class="n">float</span><span class="p">)</span>
<span class="n">y</span><span class="o">.</span><span class="n">backward</span><span class="p">(</span><span class="n">v</span><span class="p">)</span>


<span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">grad</span><span class="p">)</span></pre>
输出：

<div class="sphx-glr-script-out highlight-none notranslate">
<div class="highlight">
<pre>tensor([1.0240e+02, 1.0240e+03, 1.0240e-01])</pre>
</div>
</div>

&nbsp;

*  `with torch.no_grad():`，**用于predic**t（me：更快和声内存？）

你可以通过将代码包裹在 `with torch.no_grad():`，来**停止对从跟踪**历史中 的 .requires_grad=True 的张量自动求导。</span>

<pre><span class="k">print</span><span class="p">(</span><span class="n">x</span><span class="o">.</span><span class="n">requires_grad</span><span class="p">)</span>
<span class="k">print</span><span class="p">((</span><span class="n">x</span> <span class="o">**</span> <span class="mi">2</span><span class="p">)</span><span class="o">.</span><span class="n">requires_grad</span><span class="p">)</span>


<span class="k">with</span> <span class="n">torch</span><span class="o">.</span><span class="n">no_grad</span><span class="p">():</span>
    <span class="k">print</span><span class="p">((</span><span class="n">x</span> <span class="o">**</span> <span class="mi">2</span><span class="p">)</span><span class="o">.</span><span class="n">requires_grad</span><span class="p">)</span></pre>
输出：

<pre>True
True
False</pre>
# 神经网络

神经网络可以通过 `torch.nn` 包来构建。

**继承`nn.Module`！**

例如，看一下数字图片识别的网络：

<img class="alignnone size-full wp-image-126" src="http://pytorchchina.com/wp-content/uploads/2018/12/mnist.png" alt="" width="759" height="209" />

这是一个简单的前馈神经网络，它接收输入，让输入一个接着一个的通过一些层，最后给出输出。

一个典型的神经网络训练过程包括以下几点：

1.定义一个包含可训练参数的神经网络

2.迭代整个输入

3.通过神经网络处理输入

4.计算损失(loss)

5.反向传播梯度到神经网络的参数

6.更新网络的参数，典型的用一个简单的更新方法：<span class="pre">weight</span> <span class="pre">=</span> <span class="pre">weight</span> <span class="pre">-</span> <span class="pre">learning_rate</span> <span class="pre">*</span><span class="pre">gradient</span>

定义神经网络

```python
import torch
import torch.nn as nn
import torch.nn.functional as F


class Net(nn.Module):

    def __init__(self):
        super(Net, self).__init__()
        # 1 input image channel, 6 output channels, 5x5 square convolution
        # kernel
        self.conv1 = nn.Conv2d(1, 6, 5)
        self.conv2 = nn.Conv2d(6, 16, 5)
        # an affine operation: y = Wx + b
        self.fc1 = nn.Linear(16 * 5 * 5, 120)
        self.fc2 = nn.Linear(120, 84)
        self.fc3 = nn.Linear(84, 10)

    def forward(self, x):
        # Max pooling over a (2, 2) window
        x = F.max_pool2d(F.relu(self.conv1(x)), (2, 2))
        # If the size is a square you can only specify a single number
        x = F.max_pool2d(F.relu(self.conv2(x)), 2)
        x = x.view(-1, self.num_flat_features(x))
        x = F.relu(self.fc1(x))
        x = F.relu(self.fc2(x))
        x = self.fc3(x)
        return x

    def num_flat_features(self, x): # like flatten() 用于展开高维数据
        size = x.size()[1:]  # all dimensions except the batch dimension
        num_features = 1
        for s in size:
            num_features *= s
        return num_features


net = Net()
print(net)
```

输出：

```python
Net(
  (conv1): Conv2d(1, 6, kernel_size=(5, 5), stride=(1, 1))
  (conv2): Conv2d(6, 16, kernel_size=(5, 5), stride=(1, 1))
  (fc1): Linear(in_features=400, out_features=120, bias=True)
  (fc2): Linear(in_features=120, out_features=84, bias=True)
  (fc3): Linear(in_features=84, out_features=10, bias=True)
)

```

* `x.view(-1, x.size()[1:].numel())`这个代替`num_flat_features`

你刚定义了一个前馈函数，然后反向传播函数被自动通过 autograd 定义了。你可以使用任何张量操作在前馈函数上。

一个模型**可训练的参数**可以通过调用 `net.parameters()` 返回：

```python
params = list(net.parameters()) 
print(len(params)) # w和b被分别计数，5个w，5个b
print(params[0].size())  # conv1's .weight

```

输出：

```python
10
torch.Size([6, 1, 5, 5])
```

让我们尝试随机生成一个 32x32 的输入。注意：期望的输入维度是 32x32 。为了使用这个网络在 MNIST 数据及上，你需要把数据集中的图片维度修改为 32x32。

```python

input = torch.randn(1, 1, 32, 32)
out = net(input) # 前向传播
print(out)
```

输出：

```python
tensor([[-0.0233,  0.0159, -0.0249,  0.1413,  0.0663,  0.0297, -0.0940, -0.0135,
          0.1003, -0.0559]], grad_fn=<AddmmBackward>)
```

**用随机的梯度来反向传播**

```python
net.zero_grad() # ？？？？？？？？？？？？？
out.backward(torch.randn(1, 10))
```

在继续之前，让我们复习一下所有见过的类。

torch.Tensor - A multi-dimensional array with support for autograd operations like backward(). Also holds the gradient w.r.t. the tensor.
nn.Module - Neural network module. Convenient way of encapsulating parameters, with helpers for moving them to GPU, exporting, loading, etc.
nn.Parameter - A kind of Tensor, that is automatically registered as a parameter when assigned as an attribute to a Module.
autograd.Function - Implements forward and backward definitions of an autograd operation. Every Tensor operation, creates at least a single Function node, that connects to functions that created a Tensor and encodes its history.

损失函数

一个损失函数需要一对输入：模型输出和目标，然后计算一个值来评估输出距离目标有多远。

有一些不同的损失函数在 nn 包中。一个简单的损失函数就是 nn.MSELoss ，这计算了均方误差。

例如：

```python
output = net(input)
target = torch.randn(10)  # a dummy target, for example
target = target.view(1, -1)  # make it the same shape as output
criterion = nn.MSELoss()

loss = criterion(output, target)
print(loss)
```

输出：

```python
tensor(1.3389, grad_fn=<MseLossBackward>)
```

现在，如果你跟随损失到反向传播路径，可以使用它的 .grad_fn 属性，你将会看到一个这样的计算图：

```python
input -> conv2d -> relu -> maxpool2d -> conv2d -> relu -> maxpool2d
      -> view -> linear -> relu -> linear -> relu -> linear
      -> MSELoss
      -> loss
```

所以，当我们调用 loss.backward()，整个图都会微分，而且所有的在图中的requires_grad=True 的张量将会让他们的 grad 张量累计梯度。

为了演示，我们将跟随以下步骤来反向传播。

```python
print(loss.grad_fn)  # MSELoss
print(loss.grad_fn.next_functions[0][0])  # Linear
print(loss.grad_fn.next_functions[0][0].next_functions[0][0])  # ReLU

```

输出：

```python
<MseLossBackward object at 0x7fab77615278>
<AddmmBackward object at 0x7fab77615940>
<AccumulateGrad object at 0x7fab77615940>
```

反向传播

为了实现反向传播损失，我们所有需要做的事情仅仅是使用 loss.backward()。你需要清空现存的梯度，**要不然都将会和现存的梯度累计到一起**。

现在我们调用 loss.backward() ，然后看一下 con1 的偏置项在反向传播之前和之后的变化。

```python
net.zero_grad()     # zeroes the gradient buffers of all parameters

print('conv1.bias.grad before backward')
print(net.conv1.bias.grad)

loss.backward()

print('conv1.bias.grad after backward')
print(net.conv1.bias.grad)
```

输出：

```python
conv1.bias.grad before backward
tensor([0., 0., 0., 0., 0., 0.])
conv1.bias.grad after backward
tensor([-0.0054,  0.0011,  0.0012,  0.0148, -0.0186,  0.0087])
```

更新神经网络参数：

最简单的更新规则就是随机梯度下降。

```python
weight = weight - learning_rate * gradient
```

我们可以使用 python 来实现这个规则：

```python
learning_rate = 0.01
for f in net.parameters():
    f.data.sub_(f.grad.data * learning_rate)
```

如果你想使用不同的更新规则，类似于 SGD, Nesterov-SGD, Adam, RMSProp, 等。为了让这可行，我们建立了一个小包：`torch.optim` 实现了所有的方法。

```python
import torch.optim as optim

# create your optimizer
optimizer = optim.SGD(net.parameters(), lr=0.01)

# in your training loop:
optimizer.zero_grad()   # zero the gradient buffers
output = net(input)
loss = criterion(output, target)
loss.backward()
optimizer.step()    # Does the update

```

## 补充

* class的`forward(self,input)`方法，可以做`__call__`使用

  ```python
  net = Net()
  output = net(input)
  ```

* 调用backward()函数**之前**都要将梯度清零，因为如果梯度不清零，pytorch中会将上次计算的梯度和本次计算的梯度**累加**。

  ```python
  net.zero_grad() 
  optimizer.zero_grad() # 有优化器则只要清除优化器中的梯度
  ```

  * 这样逻辑的好处是，当我们的硬件限制不能使用更大的bachsize时，使用多次计算较小的bachsize的梯度平均值来代替（可以变相提高batch_size），更方便，坏处当然是每次都要清零梯度

* 类中定义的对象属性（可训练的）中的属性/方法

  * `net.conv1.bias.grad/net.conv1.bias.data`

  * `net.conv1.weight.grad/net.conv1.weight.data`

  * `net.parameters()`中的属性

    ```python
    for f in net.parameters():
        f.data.sub_(f.grad.data * learning_rate)
    ```

# 图像分类器/并行&GPU

你已经了解了如何定义神经网络，计算损失值和网络里权重的更新。

<h3>现在你也许会想应该怎么处理数据？</h3>

通常来说，当你处理图像，文本，语音或者视频数据时，你可以使用标准 python 包将数据加载成 numpy 数组格式，然后将这个数组转换成 torch.Tensor

<ul>
 	<li>对于图像，可以用 Pillow，OpenCV</li>
 	<li>对于语音，可以用 scipy，librosa</li>
 	<li>对于文本，可以直接用 Python 或 Cython 基础数据加载模块，或者用 NLTK 和 SpaCy</li>
</ul>

特别是对于视觉，我们已经创建了一个叫做 totchvision 的包，该包含有支持加载类似Imagenet，CIFAR10，MNIST 等公共数据集的数据**加载**模块 torchvision.datasets 和支持加载图像数据数据**转换**模块 torch.utils.data.DataLoader。

这提供了极大的便利，并且避免了编写“样板代码”。

对于本教程，我们将使用CIFAR10数据集，它包含十个类别：‘airplane’, ‘automobile’, ‘bird’, ‘cat’, ‘deer’, ‘dog’, ‘frog’, ‘horse’, ‘ship’, ‘truck’。CIFAR-10 中的图像尺寸为3*32*32，也就是RGB的3层颜色通道，每层通道内的尺寸为32*32。

<img class="alignnone size-full wp-image-116" src="http://pytorchchina.com/wp-content/uploads/2018/12/cifar10.png" alt="" width="472" height="369" />

<h3>训练一个图像分类器</h3>

我们将按次序的做如下几步：

<ol>
 	<li>使用torchvision加载并且归一化CIFAR10的训练和测试数据集</li>
 	<li>定义一个卷积神经网络</li>
 	<li>定义一个损失函数</li>
 	<li>在训练样本数据上训练网络</li>
 	<li>在测试样本数据上测试网络</li>
</ol>

加载并归一化 CIFAR10
使用 torchvision ,用它来加载 CIFAR10 数据非常简单。

```python
import torch
import torchvision
import torchvision.transforms as transforms
```

torchvision 数据集的输出是范围在[0,1]之间的 PILImage，我们将他们转换成归一化范围为[-1,1]之间的张量 Tensors。

```python
transform = transforms.Compose(
    [transforms.ToTensor(),
     transforms.Normalize((0.5, 0.5, 0.5), (0.5, 0.5, 0.5))])

trainset = torchvision.datasets.CIFAR10(root='./data', train=True,
                                        download=True, transform=transform)
trainloader = torch.utils.data.DataLoader(trainset, batch_size=4,
                                          shuffle=True, num_workers=2)

testset = torchvision.datasets.CIFAR10(root='./data', train=False,
                                       download=True, transform=transform)
testloader = torch.utils.data.DataLoader(testset, batch_size=4,
                                         shuffle=False, num_workers=2)

classes = ('plane', 'car', 'bird', 'cat',
           'deer', 'dog', 'frog', 'horse', 'ship', 'truck')

```

输出：

```python
Downloading https://www.cs.toronto.edu/~kriz/cifar-10-python.tar.gz to ./data/cifar-10-python.tar.gz
Files already downloaded and verified
```

让我们来展示其中的一些训练图片。

```python
import matplotlib.pyplot as plt
import numpy as np

# functions to show an image


def imshow(img):
    img = img / 2 + 0.5     # unnormalize
    npimg = img.numpy()
    plt.imshow(np.transpose(npimg, (1, 2, 0)))
    plt.show()


# get some random training images
dataiter = iter(trainloader)
images, labels = dataiter.next()

# show images
imshow(torchvision.utils.make_grid(images))
# print labels
print(' '.join('%5s' % classes[labels[j]] for j in range(4)))

```

输出：

```python
cat plane  ship  frog

```

<div>定义一个卷积神经网络
在这之前先 从神经网络章节 复制神经网络，并修改它为3通道的图片(在此之前它被定义为1通道)</div>

1. 
   ```python
   import torch.nn as nn
   import torch.nn.functional as F
   
   
   class Net(nn.Module):
       def __init__(self):
           super(Net, self).__init__()
           self.conv1 = nn.Conv2d(3, 6, 5)
           self.pool = nn.MaxPool2d(2, 2)
           self.conv2 = nn.Conv2d(6, 16, 5)
           self.fc1 = nn.Linear(16 * 5 * 5, 120)
           self.fc2 = nn.Linear(120, 84)
           self.fc3 = nn.Linear(84, 10)
   
       def forward(self, x):
           x = self.pool(F.relu(self.conv1(x)))
           x = self.pool(F.relu(self.conv2(x)))
           x = x.view(-1, 16 * 5 * 5)
           x = F.relu(self.fc1(x))
           x = F.relu(self.fc2(x))
           x = self.fc3(x)
           return x
   
   
   net = Net()
   ```



<div>定义一个损失函数和优化器
让我们使用分类交叉熵Cross-Entropy 作损失函数，动量SGD做优化器。</div>


```python
import torch.optim as optim

criterion = nn.CrossEntropyLoss()
optimizer = optim.SGD(net.parameters(), lr=0.001, momentum=0.9)
```

<div>训练网络
这里事情开始变得有趣，我们只需要在数据迭代器上循环传给网络和优化器 输入就可以。</div>
<div></div>

```python
for epoch in range(2):  # loop over the dataset multiple times

    running_loss = 0.0
    for i, data in enumerate(trainloader, 0):
        # get the inputs
        inputs, labels = data

        # zero the parameter gradients
        optimizer.zero_grad()

        # forward + backward + optimize
        outputs = net(inputs)
        loss = criterion(outputs, labels)
        loss.backward()
        optimizer.step()

        # print statistics
        running_loss += loss.item()
        if i % 2000 == 1999:    # print every 2000 mini-batches
            print('[%d, %5d] loss: %.3f' %
                  (epoch + 1, i + 1, running_loss / 2000))
            running_loss = 0.0

print('Finished Training')
```


输出：

```
[1,  2000] loss: 2.187
[1,  4000] loss: 1.852
[1,  6000] loss: 1.672
[1,  8000] loss: 1.566
[1, 10000] loss: 1.490
[1, 12000] loss: 1.461
[2,  2000] loss: 1.389
[2,  4000] loss: 1.364
[2,  6000] loss: 1.343
[2,  8000] loss: 1.318
[2, 10000] loss: 1.282
[2, 12000] loss: 1.286
Finished Training

```


在测试集上测试网络
我们已经通过训练数据集对网络进行了2次训练，但是我们需要检查网络是否已经学到了东西。

我们将用神经网络的输出作为预测的类标来检查网络的预测性能，用样本的真实类标来校对。如果预测是正确的，我们将样本添加到正确预测的列表里。

好的，第一步，让我们从测试集中显示一张图像来熟悉它。<img class="alignnone size-full wp-image-118" src="http://pytorchchina.com/wp-content/uploads/2018/12/sphx_glr_cifar10_tutorial_002.png" alt="" width="640" height="480" />

输出：

```python
GroundTruth:    cat  ship  ship plane
```

现在让我们看看 神经网络认为这些样本应该预测成什么：

```python
outputs = net(images)
```

输出是预测与十个类的近似程度，与某一个类的近似程度越高，网络就越认为图像是属于这一类别。所以让我们打印其中最相似类别类标：

```python
_, predicted = torch.max(outputs, 1)

print('Predicted: ', ' '.join('%5s' % classes[predicted[j]]
                              for j in range(4)))

```

输出：

```python
Predicted:    cat  ship   car  ship

```

结果看起开非常好，让我们看看网络在整个数据集上的表现。

```python
correct = 0
total = 0
with torch.no_grad():
    for data in testloader:
        images, labels = data
        outputs = net(images)
        _, predicted = torch.max(outputs.data, 1)
        total += labels.size(0)
        correct += (predicted == labels).sum().item()

print('Accuracy of the network on the 10000 test images: %d %%' % (
    100 * correct / total))
```

输出：

```python
Accuracy of the network on the 10000 test images: 54 %
```

这看起来比随机预测要好，随机预测的准确率为10%（随机预测出为10类中的哪一类）。看来网络学到了东西。

```python
class_correct = list(0. for i in range(10))
class_total = list(0. for i in range(10))
with torch.no_grad():
    for data in testloader:
        images, labels = data
        outputs = net(images)
        _, predicted = torch.max(outputs, 1)
        c = (predicted == labels).squeeze()
        for i in range(4):
            label = labels[i]
            class_correct[label] += c[i].item()
            class_total[label] += 1


for i in range(10):
    print('Accuracy of %5s : %2d %%' % (
        classes[i], 100 * class_correct[i] / class_total[i]))
```

输出：

<pre>Accuracy of plane : 57 %
Accuracy of   car : 73 %
Accuracy of  bird : 49 %
Accuracy of   cat : 54 %
Accuracy of  deer : 18 %
Accuracy of   dog : 20 %
Accuracy of  frog : 58 %
Accuracy of horse : 74 %
Accuracy of  ship : 70 %
Accuracy of truck : 66 %</pre>
* 在GPU上训练
  就像你怎么把一个张量转移到GPU上一样，你要将神经网络转到GPU上。
  如果CUDA可以用，让我们首先定义下我们的设备为第一个可见的cuda设备。

```python
device = torch.device("cuda:0" if torch.cuda.is_available() else "cpu")
# Assume that we are on a CUDA machine, then this should print a CUDA device:
print(device)
```

输出：

<div class="sphx-glr-script-out highlight-none notranslate">
<div class="highlight">
<pre>cuda:0
</pre>
</div>
</div>


本节剩余部分都会假定设备就是台CUDA设备。

接着这些方法会**递归地遍历所有模块，并将它们的参数和缓冲器**转换为CUDA张量。

<div class="code python highlight-default notranslate">
<div class="highlight">
<pre><span class="n">net</span><span class="o">.</span><span class="n">to</span><span class="p">(</span><span class="n">device</span><span class="p">)</span>
</pre>
</div>
</div>

记住你也必须在每一个步骤向GPU发送输入和目标：

<div class="code python highlight-default notranslate">
<div class="highlight">
<pre><span class="n">inputs</span><span class="p">,</span> <span class="n">labels</span> <span class="o">=</span> <span class="n">inputs</span><span class="o">.</span><span class="n">to</span><span class="p">(</span><span class="n">device</span><span class="p">),</span> <span class="n">labels</span><span class="o">.</span><span class="n">to</span><span class="p">(</span><span class="n">device</span><span class="p">)</span>
</pre>
</div>
</div>

为什么没有注意到与CPU相比巨大的加速？因为你的网络非常小。

<strong> tensor和net都有`.to`方法传入参数device</strong>

<strong>练习：</strong>尝试增加你的网络宽度（首个 nn.Conv2d 参数设定为 2，第二个nn.Conv2d参数设定为1--它们需要有相同的个数），看看会得到怎么的速度提升。

<strong>目标：</strong>

<ul>
 	<li>深度理解了PyTorch的张量和神经网络</li>
 	<li>训练了一个小的神经网络来分类图像</li>
</ul>
在多个GPU上训练

如果你想要来看到大规模加速，使用你的所有GPU，请查看：数据并行性（https://pytorch.org/tutorials/beginner/blitz/data_parallel_tutorial.html）。PyTorch 60 分钟入门教程：数据并行处理

http://pytorchchina.com/2018/12/11/optional-data-parallelism/

## other

* torch中返回的数值都是tensor，可以调用相关方法，使用item提取值（**只对单个元素的tensor**）
* `torch.max(tensor,d)`：返回最大的数；如果传入d表示对对应维度提取最大值，会返回对应最大值，也会返回最大值的index（也有`torch.argmax`）
* 模型装入gpu后，传入的数据也需装入gpu（使用`.to`方法）
* **cuda**
  * 构造一个设备`device = torch.device("cuda")/device = torch.device("cuda:0")/device = torch.device("cuda:0" if torch.cuda.is_available() else "cpu")`
  * model和data都有`.to`方法，可以装入设备`input = data.to(device)/ model.to(device)`
    * me：device中的model应该是处理对应device中的数据，可能需要在装入cpu中`data.to(torch.device('cpu'))`
    * `data.device.type`可以查看数据对应设备（字符串）
    * **数据并行处理`model = nn.DataParallel(model)`：**只对model处理即可，data还是普通的装入device

# 数据加载和处理

* **数据存放方式**：使用一个csv文件存放数据路径信息；Dataset的init加载csv文件到内存；getitem加载文件到内存，以节省内存空间

* *从文件中读取时会自动根据文件夹分类吗？？？*

* `torch.utils.data.Dataset`是表示数据集的抽象类，因此自定义数据集应**继承**Dataset并**覆盖**以下方法 

  *  `__len__` 实现 `len(dataset)` 返还数据集的尺寸
  * `__getitem__`用来获取一些索引数据，例如 `dataset[i]` 中的(i)

* **DataLoader：**`torch.utils.data.DataLoader(某个Dataset,batch_size=,shuffle=True,num_workers= )`

  * 用于生成对dataset的迭代器

  * `inputs, classes = next(iter(dataloaders['train']))`：注意返回值的形式**data+labels**

  * **DataLoader的num_works参数设置（可以多线程load）：是告诉DataLoader实例要使用多少个子进程进行数据加载(和CPU有关，和GPU无关)**

    > [Pytorch dataloader中的num_workers (选择最合适的num_workers值)_hxxjxw的博客-CSDN博客_dataloader num_workers](https://blog.csdn.net/hxxjxw/article/details/119531239)

    * 数据集较小时（小于2W）建议num_works不用管默认就行，因为用了反而比没用慢。

    * 当数据集较大时建议采用，**num_works一般设置为（CPU线程数+-1）为最佳**，可以用以下代码找出最佳num_works

    ```python
    import time
    import torch.utils.data as d
    import torchvision
    import torchvision.transforms as transforms
     
     
    if __name__ == '__main__':
        BATCH_SIZE = 100
        transform = transforms.Compose([transforms.ToTensor(),
                                        transforms.Normalize((0.5,), (0.5,))])
        train_set = torchvision.datasets.MNIST('\mnist', download=False, train=True, transform=transform)
        
        # data loaders
        train_loader = d.DataLoader(train_set, batch_size=BATCH_SIZE, shuffle=True)
        
        for num_workers in range(20):
            train_loader = d.DataLoader(train_set, batch_size=BATCH_SIZE, shuffle=True, num_workers=num_workers)
            # training ...
            start = time.time()
            for epoch in range(1):
                for step, (batch_x, batch_y) in enumerate(train_loader):
                    pass
            end = time.time()
            print('num_workers is {} and it took {} seconds'.format(num_workers, end - start))
    ```

    * *为什么会影响训练？？？*

  * **DataLoader的`collate_fn`参数设置**

    > [Pytorch技巧1：DataLoader的collate_fn参数](https://blog.csdn.net/weixin_42028364/article/details/81675021?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2~default~CTRLIST~Rate-1-81675021-blog-125455498.pc_relevant_multi_platform_whitelistv3&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~CTRLIST~Rate-1-81675021-blog-125455498.pc_relevant_multi_platform_whitelistv3&utm_relevant_index=2)
    >
    > 一个值得关注的参数是`collate_fn`, 可以通过它来决定如何对数据进行**批处理**。但是绝大多数情况下默认值就能运行良好。

  * DataLoader返回的对象每个成员的中都有batch_size条数据

## other

* torch喜欢把channel放在第一维（tensorflow相反）

* 注意windows用户如果要使用**多核多线程**必须把训练放在`if __name__ == '__main__':`下才不会报错！！！（me：Dataloader中的num_works吗？）

* 忽略警告

  ```python
  # 忽略警告
  import warnings
  warnings.filterwarnings("ignore")
  ```

* pandas的数据类型为`'pandas.core.frame.DataFrame'`

  * 使用`.iloc`进行基于整数位置的**索引**或者选择
  * 使用`.ioc`进行按照标签或者索引、布尔值或者条件进行选择数据，这种选择数据的方法较为常用
  * 后面都是跟`[]`

* `**`/`*`解包参数

# 小试牛刀(简单MLP模型)

* Numpy是一个很棒的框架，但它不能利用GPU来加速其数值计算。 对于现代深度神经网络，GPU通常提供50倍或更高的加速，所以，numpy不能满足当代深度学习的需求。

* 但是可以使用自动微分来自动计算神经网络中的后向传递。 PyTorch中的 `autograd`包提供了这个功能。当使用autograd时，网络前向传播将定义一个**计算图**；**图中的节点是tensor，边是函数**， 这些函数是输出tensor到输入tensor的映射。这张计算图使得在网络中反向传播时梯度的计算十分简单。

  如果我们想计算某些的tensor的梯度，我们只需要在建立这个tensor时加入这么一句：`requires_grad=True`。这个tensor上的任何PyTorch的操作都将构造一个计算图，从而允许我们稍后在图中执行反向传播。如果这个`tensor x`的`requires_grad=True`，那么反向传播之后`x.grad`将会是另一个张量，其为x关于某个**标量值**的梯度。

  * **使用`torch.no_grad()`上下文管理器防止PyTorch为更新构建计算图**（放与反向传播无关的运算）
  * 反向传播更新完参数值后要将grad更新为0：`w1.grad.zero_()`

* 需要上传到GPU的数据

  * 使用GPU的方法

    ```python
    use_gpu = torch.cuda.is_available() # 判断是否可以使用GPU
    with torch.cuda.device(1):
        # allocates a tensor on GPU 1
        a = torch.tensor([1., 2.], device=cuda)
     
        # transfers a tensor from CPU to GPU 1
        b = torch.tensor([1., 2.]).cuda()
        # a.device and b.device are device(type='cuda', index=1)
     
        # You can also use ``Tensor.to`` to transfer a tensor:
        b2 = torch.tensor([1., 2.]).to(device=cuda)
        # b.device and b2.device are device(type='cuda', index=1)
     
    #这三种方式没什么区别，但都需要先判断是否又GPU才能使用，个人觉得.to(device)更好用，在使用前先使用（1）中的代码判断，后面直接使用use_gpu即可。
    ```

  * 构建网络时，把**网络与损失**函数转换到GPU上

  * 训练网络时，把（**训练数据data&label**）数据转换到GPU上

  * 只有tensor类型才能上传到GPU上，故需要对numpy数据进行转换成tensor类型；对训练的输出结果有些需要使用np的函数进行操作，需先将输出结果转到CPU上，并转成numpy类型，再使用np的函数

* nn模块（**Sequential形式**，`torch.nn.Sequential()`），损失函数，优化器（`optim`）的例子

  ```python
  import torch
  
  # N是批大小；D是输入维度
  # H是隐藏层维度；D_out是输出维度
  N, D_in, H, D_out = 64, 1000, 100, 10
  
  # 产生随机输入和输出张量
  x = torch.randn(N, D_in)
  y = torch.randn(N, D_out)
  
  # 使用nn包定义模型和损失函数
  model = torch.nn.Sequential(
            torch.nn.Linear(D_in, H),
            torch.nn.ReLU(),
            torch.nn.Linear(H, D_out),
          )
  loss_fn = torch.nn.MSELoss(reduction='sum')
  
  # 使用optim包定义优化器（Optimizer）。Optimizer将会为我们更新模型的权重。
  # 这里我们使用Adam优化方法；optim包还包含了许多别的优化算法。
  # Adam构造函数的第一个参数告诉优化器应该更新哪些张量。
  learning_rate = 1e-4
  optimizer = torch.optim.Adam(model.parameters(), lr=learning_rate) # 使用方式！！！
  
  for t in range(500):
      # 前向传播：通过像模型输入x计算预测的y
      y_pred = model(x)
  
      # 计算并打印loss
      loss = loss_fn(y_pred, y)
      print(t, loss.item())
  
      # 在反向传播之前，使用optimizer将它要更新的所有张量的梯度清零(这些张量是模型可学习的权重)
      optimizer.zero_grad()
      # 反向传播：根据模型的参数计算loss的梯度
      loss.backward()
      # 调用Optimizer的step函数使它所有参数更新
      optimizer.step()
  ```

* nn模块（子类形式，继承`torch.nn.Module`）

  * 注意上面和下面model`ReLU`的方式
  * 可以操作控制流，且可以重用同一模块

  ```python
  import random
  import torch
  
  class DynamicNet(torch.nn.Module):
      def __init__(self, D_in, H, D_out):
          """
          在构造函数中，我们构造了三个nn.Linear实例，它们将在前向传播时被使用。
          """
          super(DynamicNet, self).__init__()
          self.input_linear = torch.nn.Linear(D_in, H)
          self.middle_linear = torch.nn.Linear(H, H)
          self.output_linear = torch.nn.Linear(H, D_out)
  
      def forward(self, x):
          """
          对于模型的前向传播，我们随机选择0、1、2、3，
          并重用了多次计算隐藏层的middle_linear模块。
          由于每个前向传播构建一个动态计算图，
          我们可以在定义模型的前向传播时使用常规Python控制流运算符，如循环或条件语句。
          在这里，我们还看到，在定义计算图形时多次重用同一个模块是完全安全的。
          这是Lua Torch的一大改进，因为Lua Torch中每个模块只能使用一次。
          """
          h_relu = self.input_linear(x).clamp(min=0) # 等同于ReLU ！
          for _ in range(random.randint(0, 3)):
              h_relu = self.middle_linear(h_relu).clamp(min=0)
          y_pred = self.output_linear(h_relu)
          return y_pred
  
  
  # N是批大小；D是输入维度
  # H是隐藏层维度；D_out是输出维度
  N, D_in, H, D_out = 64, 1000, 100, 10
  
  # 产生输入和输出随机张量
  x = torch.randn(N, D_in)
  y = torch.randn(N, D_out)
  
  # 实例化上面定义的类来构造我们的模型
  model = DynamicNet(D_in, H, D_out)
  
  # 构造我们的损失函数（loss function）和优化器（Optimizer）。
  # 用平凡的随机梯度下降训练这个奇怪的模型是困难的，所以我们使用了momentum方法。
  criterion = torch.nn.MSELoss(reduction='sum')
  optimizer = torch.optim.SGD(model.parameters(), lr=1e-4, momentum=0.9)
  for t in range(500):
  
      # 前向传播：通过向模型传入x计算预测的y。
      y_pred = model(x)
  
      # 计算并打印损失
      loss = criterion(y_pred, y)
      print(t, loss.item())
  
      # 清零梯度，反向传播，更新权重 
      optimizer.zero_grad()
      loss.backward()
      optimizer.step()
  ```


# 迁移学习

- 两种场景
  - 微调Convnet：使用预训练的网络(如在`imagenet 1000`上训练而来的网络)来**初始化自己的网络**，而不是随机初始化。其他的训练步骤不变。
  - 将Convnet看成固定的特征提取器:首先固定ConvNet除了最后的全连接层外的其他所有层。**最后的全连接层被替换成一个新的随机初始化的层**，只有这个新的层会被训练[只有这层参数会在反向传播时更新]
- `pretrained`通过`True`或者`False`来决定是否使用预训练好的权重
  - 在默认状态下`pretrained = False`，意味着我们不使用预训练得到的权重，只使用**网络结构**
  - 当`pretrained = True`，意味着我们将使用在一些数据集上**网络结构**和**预训练得到的权重**
- 

# 保存加载模型

> [保存和加载模型 - PyTorch官方教程中文版 (pytorch123.com)](https://pytorch123.com/ThirdSection/SaveModel/)

* `模型.state_dict`：返回字典，(只)包含可学习参数的层的名称和值

  * 获得对应值的数据`model.state_dict()[param_tensor]`

* `优化器.state_dict`：返回优化器状态信息，超参数等信息

* 在 PyTorch 中最常见的模型保存使`.pt`或者是`.pth`作为模型文件扩展名。

* PyTorch 中常见的保存checkpoint 是使用 `.tar `文件扩展名。

* **evaluate：***请记住，在运行推理之前，务必调用`model.eval()`设置 dropout 和 batch normalization 层为评估模式。如果不这么做，可能导致模型推断结果不一致。（在test时关闭dropout和统一batch normalization参数？？？）*

* **train：**如果你想要恢复训练，请调用`model.train()`以确保这些层处于训练模式。

* 保存和加载模型的两种方式

  * 只保存参数，不保存模型，对应的保存和加载方法分别是：（官方推荐，原因自然是保存的内容少，速度会更快。还可以同时保存模型的训练参数epoch、loss、optimizer等）
  
    ```python
    ## 保存训练完的网络的各层参数，保存训练完的网络的各层参数（即weights和bias)
    torch.save(net.state_dict(),path)
    ##加载保存到path中的各层参数到神经网络net2，不可以直接为torch.load_state_dict(path)，此函数不能直接接收字符串类型参数
    net2.load_state_dict(torch.load(path))
    ```
  
  * 存模型和参数，对应的保存和加载方法分别是：
  
    ```python
    ## 保存训练完的整个网络模型（不止weights和bias，还有模型本身）
    torch.save(net,path)
    ## 加载保存到path中的整个神经网络
    net2=torch.load(path)
    ```
  
* model和optimizer的容器，传入**词典**

  ```python
  torch.save({
              'modelA_state_dict': modelA.state_dict(),
              'modelB_state_dict': modelB.state_dict(),
              'optimizerA_state_dict': optimizerA.state_dict(),
              'optimizerB_state_dict': optimizerB.state_dict(),
              ...
              }, PATH)
  
  modelA = TheModelAClass(*args, **kwargs)
  modelB = TheModelBClass(*args, **kwargs)
  optimizerA = TheOptimizerAClass(*args, **kwargs)
  optimizerB = TheOptimizerBClass(*args, **kwargs)
  
  checkpoint = torch.load(PATH)
  modelA.load_state_dict(checkpoint['modelA_state_dict'])
  modelB.load_state_dict(checkpoint['modelB_state_dict'])
  optimizerA.load_state_dict(checkpoint['optimizerA_state_dict'])
  optimizerB.load_state_dict(checkpoint['optimizerB_state_dict'])
  
  modelA.eval()
  modelB.eval()
  # - or -
  modelA.train()
  modelB.train()
  ```


# 混合前端seq2seq模型部署

* encoder-decoder结构

  ![](https://camo.githubusercontent.com/c18710d5b9b830f16e4c3c8efc8690b3c99d3b66d786278ef3e5ff85afdac261/68747470733a2f2f75706c6f61642d696d616765732e6a69616e7368752e696f2f75706c6f61645f696d616765732f31373338373030312d383466366331666233316566323236312e706e673f696d6167654d6f6772322f6175746f2d6f7269656e742f7374726970253743696d61676556696577322f322f772f31323430)

  
