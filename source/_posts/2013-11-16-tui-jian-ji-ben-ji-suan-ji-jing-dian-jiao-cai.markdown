---
layout: post
title: "推荐几本计算机经典教材"
date: 2013-11-16 09:30
comments: true
categories: 
---
<pre>
	<code class="python">
$ cd octopress
$ rake install
	</code>
</pre>

<figure class='code'> <div class="highlight"><table><tr><td class="gutter"><pre class="line-numbers"><span class='line-number'>1</span>
<span class='line-number'>2</span>
<span class='line-number'>3</span>
<span class='line-number'>4</span>
<span class='line-number'>5</span>
<span class='line-number'>6</span>
<span class='line-number'>7</span>
<span class='line-number'>8</span>
<span class='line-number'>9</span>
<span class='line-number'>10</span>
<span class='line-number'>11</span>
<span class='line-number'>12</span>
<span class='line-number'>13</span>
<span class='line-number'>14</span>
</pre></td><td class='code'><pre><code class='python'><span class='line'>    <span class="k">while</span> <span class="bp">True</span><span class="p">:</span>
</span><span class='line'>        <span class="k">try</span><span class="p">:</span>
</span><span class='line'>            <span class="n">print_stdout</span><span class="p">(</span><span class="n">process</span><span class="p">)</span>
</span><span class='line'>            <span class="n">max_mtime</span> <span class="o">=</span> <span class="nb">max</span><span class="p">(</span><span class="n">file_times</span><span class="p">(</span><span class="n">PATH</span><span class="p">,</span><span class="n">extension</span><span class="p">))</span>
</span><span class='line'>            <span class="k">if</span> <span class="n">max_mtime</span> <span class="o">&gt;</span> <span class="n">last_mtime</span><span class="p">:</span>
</span><span class='line'>                <span class="n">last_mtime</span> <span class="o">=</span> <span class="n">max_mtime</span>
</span><span class='line'>                <span class="k">print</span> <span class="s">&#39;Restarting process...&#39;</span>
</span><span class='line'>                <span class="n">stop_process</span><span class="p">(</span><span class="n">process</span><span class="p">)</span>
</span><span class='line'>                <span class="n">process</span> <span class="o">=</span> <span class="n">start_process</span><span class="p">(</span><span class="n">command</span><span class="p">)</span>
</span><span class='line'>            <span class="n">time</span><span class="o">.</span><span class="n">sleep</span><span class="p">(</span><span class="n">WAIT</span><span class="p">)</span>
</span><span class='line'>        <span class="k">except</span> <span class="p">(</span><span class="ne">KeyboardInterrupt</span><span class="p">,</span> <span class="ne">SystemExit</span><span class="p">):</span>
</span><span class='line'>                <span class="k">print</span> <span class="s">&quot;Caught KeyboardInterrupt, terminating process&quot;</span>
</span><span class='line'>                <span class="n">stop_process</span><span class="p">(</span><span class="n">process</span><span class="p">)</span>
</span><span class='line'>                <span class="k">break</span>
</span></code></pre></td></tr></table></div></figure>
