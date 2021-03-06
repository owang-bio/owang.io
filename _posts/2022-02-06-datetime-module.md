---
keywords: fastai
description: datetime module, strftime() and strptime().
title: Python Datetime Module
toc: true
badges: true
comments: false
categories: [python, datetime]
nb_path: _notebooks/2022-02-06-datetime-module.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2022-02-06-datetime-module.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>I am dealing with time series data every day. So, the first Python module I want to mention is datetime which provides basic classes for dates and time manipulation.</p>
<p>I am helping several international markets with forecasting, but most of the time I don’t need to worry about time zone or daylight saving time, etc. If you are interested in the datetime type that include such information, you can learn more about it from the <a href="https://docs.python.org/3/library/datetime.html#date-objects">documentation</a>.</p>
<p>In this post, I will introduce several basic classes and class methods in datetime module that I use the most frequently.</p>
<p>Of course, to use this module, we first need to import it:</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="kn">import</span> <span class="nn">datetime</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="datetime()">datetime()<a class="anchor-link" href="#datetime()"> </a></h2><p>One useful class in datetime module is datetime(). When instantiating, the arguments, year, month and day are required, and the others are optional, for example:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><strong>datetime(year, month, day[, hour[, minute[, second[, microsecond[,tzinfo]]]]])</strong></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>This instantiates a datetime object which has these attributes: year, month, day, hour, minute, second, microsecond, and tzinfo. For example, the following code returns the datetime object:</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">dt</span> <span class="o">=</span> <span class="n">datetime</span><span class="o">.</span><span class="n">datetime</span><span class="p">(</span><span class="mi">2021</span><span class="p">,</span> <span class="mi">6</span><span class="p">,</span> <span class="mi">1</span><span class="p">)</span>
<span class="n">dt</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>datetime.datetime(2021, 6, 1, 0, 0)</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>The following code is how we can access it’s year, month and day attributes, and you can access the other attributes using the dot notation. They are all integers. For example:</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">dt</span><span class="o">.</span><span class="n">year</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>2021</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">dt</span><span class="o">.</span><span class="n">month</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>6</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">dt</span><span class="o">.</span><span class="n">day</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>1</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="date()">date()<a class="anchor-link" href="#date()"> </a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Another class that I use frequently is date(). It is very similar to datetime() class, but when we instantiate it, it only takes three arguments: year, month, day. They way to access it’s attribute is the same as that of datetime objects. For example:</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">dt</span> <span class="o">=</span> <span class="n">datetime</span><span class="o">.</span><span class="n">date</span><span class="p">(</span><span class="mi">2021</span><span class="p">,</span> <span class="mi">6</span><span class="p">,</span> <span class="mi">1</span><span class="p">)</span>
<span class="n">dt</span><span class="o">.</span><span class="n">year</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>2021</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>date() class has a today() method, it does not take any arguments, but return the today’s date in local time:</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">datetime</span><span class="o">.</span><span class="n">date</span><span class="o">.</span><span class="n">today</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>datetime.date(2022, 2, 7)</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="strftime()-and-strptime()">strftime() and strptime()<a class="anchor-link" href="#strftime()-and-strptime()"> </a></h2>
</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Sometime we need to convert date/datetime objects into string format or vice versa, which is when strftime() and strptime() come in handy. date/datetime objects have a strftime() method that converts them into strings, in a format that we can specify. For example:</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">dt</span> <span class="o">=</span> <span class="n">datetime</span><span class="o">.</span><span class="n">date</span><span class="p">(</span><span class="mi">2021</span><span class="p">,</span> <span class="mi">6</span><span class="p">,</span> <span class="mi">1</span><span class="p">)</span> <span class="c1">#create a date object</span>
<span class="n">dt</span><span class="o">.</span><span class="n">strftime</span><span class="p">(</span><span class="s1">&#39;%Y-%m-</span><span class="si">%d</span><span class="s1">&#39;</span><span class="p">)</span> <span class="c1">#convert the date to string</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;2021-06-01&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>“%Y”, “%m”, and “%d” are format codes. For example, with “%Y” you are telling the strftime() to convert the year into format of “2021”. You can read more details about the format codes <a href="https://docs.python.org/3/library/datetime.html#strftime-and-strptime-behavior">here</a>. If we want the date string in the format of “June-01-21”, we can use format code of “%B-%d-%y”:</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">dt</span><span class="o">.</span><span class="n">strftime</span><span class="p">(</span><span class="nb">format</span><span class="o">=</span><span class="s2">&quot;%B-</span><span class="si">%d</span><span class="s2">-%y&quot;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>&#39;June-01-21&#39;</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>strptime() is a class method of datetime objects. So, to use this method, you need to call:</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p><strong>datetime.datetime.strptime(datetime_in_str, '%Y-%m-%d')</strong></p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>For example:</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">datetime</span><span class="o">.</span><span class="n">datetime</span><span class="o">.</span><span class="n">strptime</span><span class="p">(</span><span class="s1">&#39;2021-06-20&#39;</span><span class="p">,</span> <span class="s1">&#39;%Y-%m-</span><span class="si">%d</span><span class="s1">&#39;</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

<div class="output_wrapper">
<div class="output">

<div class="output_area">



<div class="output_text output_subarea output_execute_result">
<pre>datetime.datetime(2021, 6, 20, 0, 0)</pre>
</div>

</div>

</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>One thing to remember is that strptime() does not take keyword arguments, which means we need to provide the date in string format as the first argument, and the format code as the second argument, and we don’t give any names to the arguments like we did for strftime (e.g. dt.strftime(format="%B-%d-%y")).</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>That’s it for the datetime module from me. Hope you it is helpful to some of you!</p>

</div>
</div>
</div>
</div>
 

