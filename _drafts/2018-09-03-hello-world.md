---
layout: post
title:  "Hello World!"
date:   2018-09-03 20:58:56 +0200
categories: jekyll test
customjs:
- static/js/manifest.2ae2e69a05c33dfc65f8.js
---
Yep, I'm up and running!

### Traditional source code formatting

```python
class TestClass(object):
    """
    This is a multiline comment that
    spans multiple lines, yey!
    """

    def __init__(self):
        self.var = 123
        self.another_var = f"string displaying {self.var}"
        self.function_call(self.var, true)

    @decorator
    def function_call(self, argument, default_arg=false):

        variable = TestClass.attribute.method(
            argument=argument,
            second_argument=default_arg
        )
        return variable
if __name__ == "__main__":
    print(b"main")
```

### Using parametric font for all text

<style>
.para { font-family: "Segoe UI"; }
.para2 { font-family: "Segoe UI"; }
</style>
<pre class="highlight"><code><span class="k para2">class</span> <span class="nc para">TestClass</span><span class="p">(</span><span class="nb para">object</span><span class="p">):</span>
    <span class="s">"""
    <span class="para">This is a multiline comment that</span>
    <span class="para">spans multiple lines, yey!</span>
    """</span>

    <span class="k para2">def</span> <span class="nf para">__init__</span><span class="p">(</span><span class="bp para">self</span><span class="p">):</span>
        <span class="bp para">self</span><span class="o">.</span><span class="n para">var</span> <span class="o">=</span> <span class="mi">123</span>
        <span class="bp para">self</span><span class="o">.</span><span class="n para">another_var</span> <span class="o">=</span> <span class="n">f</span><span class="s">"<span class="para">string displaying</span> {<span class="para">self</span>.<span class="para">var</span>}"</span>
        <span class="bp para">self</span><span class="o">.</span><span class="n para">function_call</span><span class="p">(</span><span class="bp para">self</span><span class="o">.</span><span class="n para">var</span><span class="p">,</span> <span class="n para2">true</span><span class="p">)</span>

    <span class="nd">@<span class="para">decorator</span></span>
    <span class="k para2">def</span> <span class="nf para">function_call</span><span class="p">(</span><span class="bp para">self</span><span class="p">,</span> <span class="n para">argument</span><span class="p">,</span> <span class="n para">default_arg</span><span class="o">=</span><span class="n para2">false</span><span class="p">):</span>

        <span class="n para">variable</span> <span class="o">=</span> <span class="n para">TestClass</span><span class="o">.</span><span class="n para">attribute</span><span class="o">.</span><span class="n para">method</span><span class="p">(</span>
            <span class="n para">argument</span><span class="o">=</span><span class="n para">argument</span><span class="p">,</span>
            <span class="n para">second_argument</span><span class="o">=</span><span class="n para">default_arg</span>
        <span class="p">)</span>
        <span class="k para2">return</span> <span class="n para">variable</span>
<span class="k para2">if</span> <span class="n para">__name__</span> <span class="o">==</span> <span class="s para">"__main__"</span><span class="p">:</span>
    <span class="k para">print</span><span class="p">(</span><span class="n">b</span><span class="s para">"main"</span><span class="p">)</span>
</code></pre>


### Remove explicit syntax

<pre class="highlight"><code><span class="k para2">class</span> <span class="nc para">TestClass</span><span class="p">(</span><span class="nb para">object</span><span class="p">)</span>
    <span class="s"><span class="para">This is a multiline comment that</span>
    <span class="para">spans multiple lines, yey!</span></span>

    <span class="k para2">def</span> <span class="nf para">__init__</span><span class="p">(</span><span class="bp para">self</span><span class="p">)</span>
        <span class="bp para">self</span><span class="o">.</span><span class="n para">var</span> <span class="o">=</span> <span class="mi">123</span>
        <span class="bp para">self</span><span class="o">.</span><span class="n para">another_var</span> <span class="o">=</span> <span class="n"></span><span class="s">"<span class="para">string displaying</span> </span>{<span class="bp para">self</span><span class="o">.</span><span class="n para">var</span>}<span class="s">"</span>
        <span class="bp para">self</span><span class="o">.</span><span class="n para">function_call</span><span class="p">(</span><span class="bp para">self</span><span class="o">.</span><span class="n para">var</span><span class="p">,</span> <span class="n para2">true</span><span class="p">)</span>

    <span class="nd">@<span class="para">decorator</span></span>
    <span class="k para2">def</span> <span class="nf para">function_call</span><span class="p">(</span><span class="bp para">self</span><span class="p">,</span> <span class="n para">argument</span><span class="p">,</span> <span class="n para">default_arg</span><span class="o">=</span><span class="n para2">false</span><span class="p">)</span>

        <span class="n para">variable</span> <span class="o">=</span> <span class="n para">TestClass</span><span class="o">.</span><span class="n para">attribute</span><span class="o">.</span><span class="n para">method</span><span class="p">(</span>
            <span class="n para">argument</span><span class="o">=</span><span class="n para">argument</span><span class="p">,</span>
            <span class="n para">second_argument</span><span class="o">=</span><span class="n para">default_arg</span>
        <span class="p">)</span>
        <span class="k para2">return</span> <span class="n para">variable</span>
<span class="k para2">if</span> <span class="n para">__name__</span> <span class="o">==</span> <span class="s para">"__main__"</span><span class="p">:</span>
    <span class="k para">print</span><span class="p">(</span><span class="n"></span><span class="s para">"main"</span><span class="p">)</span>
</code></pre>




{% include hough.html %}

```python
this_variable_equals = [
    name,
    "some string",
    [123412341243, 3.141592653589793238462, -5.4321e10]
]
```

<head>
  <link href="/code-viewer/static/css/app.2657c6bad78516b5c444821a9bce0553.css" rel="stylesheet">
</head>
<div id="app"></div>
<script type="text/javascript" src="/code-viewer/static/js/manifest.2ae2e69a05c33dfc65f8.js"></script>
<script type="text/javascript" src="/code-viewer/static/js/vendor.b8580e1294724b76ff58.js"></script>
<script type="text/javascript" src="/code-viewer/static/js/app.18f374775a69b2498002.js"></script>
