# AKMaskField

<p>AKMaskField is Swift plugin.</p>
<p>AKMaskField allows a user to more easily enter fixed width input where you would like them to enter the data in a certain format (dates,phone numbers, etc)</p>
<p><b>Features:</b></p>
<ul class="task-list">
<li>easy to use from code or storyboard</li>
<li>smart mask placeholder</li>
<li>mask field status callbacks</li>
<li>lots of delegates</li>
<li>regex-mask support</li>
<li>dynamic-mask support</li>
<li>fast field processing</li>
<li>smart copy/past text features</li>
</ul>
<h2><a id="user-content-demo" class="anchor" href="#demo" aria-hidden="true"><span class="octicon octicon-link"></span></a>Demo</h2>
<img src="https://raw.githubusercontent.com/artemkrachulov/AKMaskField/master/Extra/preview.png" alt="preview.png">
<h2><a id="user-content-usage" class="anchor" href="#usage" aria-hidden="true"><span class="octicon octicon-link"></span></a>Usage</h2>
<p>Include AKMaskField.swift file to your project. Set UITextField as AKMaskField custom class. Define your masks properties:</p>
<p><b>Code:</b></p>
<pre><code>
self.filed.mask = "{dddd}-{DDDD}-{WaWa}-{aaaa}"
self.filed.maskShow = true
self.filed.maskPlaceholder = "xxxx-xxxx-xxxx-xxxx"
</code></pre>
<p><b>Storyboard:</b></p>
<pre><code>
Mask: {dddd}-{DDDD}-{WaWa}-{aaaa}
Mask Show: On
Mask Placeholder = xxxx-xxxx-xxxx-xxxx
</code></pre>
<h2><a id="user-content-properties" class="anchor" href="#properties" aria-hidden="true"><span class="octicon octicon-link"></span></a>Properties</h2>
<h3><a id="user-content-masks" class="anchor" href="#static-masks" aria-hidden="true"><span class="octicon octicon-link"></span></a>Mask</h3>
<p><code>.mask</code> or <code>Mask</code></p>
<p>String property which define whole mask text. Text contain blocks with characters and any text outside blocks. All mask blocks must be defined in brackets <code>{</code> ... <code>}</code>.</p>
<p>Example:</p>
<pre><code>
{dddd}-{ddddd}-{dddd}-{dddd}

</code></pre>
<br>
<p>Each character may be validated by type. The following mask definitions are predefined:</p>
<ul class="task-list">
<li><b>d</b> - Number, Decimal Digit</li>
<li><b>D</b> - Match any character that is not a decimal digit</li>
<li><b>W</b> - Match a non-word character</li>
<li><b>a</b> - Match alphabet</li>
<li><b>.</b> - Match any character (default)</li>
</ul>
<p>Example:</p>
<pre><code>
{dddd}-{DDDD}-{WaWa}-{aaaa}

</code></pre>
<br>
<h3><a id="user-content-show" class="anchor" href="#static-show" aria-hidden="true"><span class="octicon octicon-link"></span></a>Show</h3>
<p><code>.maskShow</code> or <code>Mask Show</code></p>
<p>Boolean property which define mask view status. Similar as default placeholder actions. Can have 2 states:</p>
<ul class="task-list">
<li><b>On (true)</b> - Mask always visible. Overrides default UITextField placeholder</li>

<li><b>Off (false)</b> - Mask visible if user type text. If mask field don't have any user text field will be empty or show default UITextField placeholder (default)</li>
</ul>
<br>
<h3><a id="user-content-placeholder" class="anchor" href="#static-placeholder" aria-hidden="true"><span class="octicon octicon-link"></span></a>Placeholder</h3>
<p><code>.maskPlaceholder</code> or <code>Mask Placeholder</code></p>
<p>String property display text which will see user. Placeholder can be:</p>
<ul class="task-list">
<li><b>1</b> character length. In this case char character will be copied to full mask lenght. (default "*")
<pre><code>
self.filed.mask = "{dddd}-{DDDD}-{WaWa}-{aaaa}"
self.filed.maskPlaceholder = "Z"

// Text in mask filed
// ZZZZ-ZZZZ-ZZZZ-ZZZZ
</code></pre>
</li>
<li><b>Same lenght</b> as mask(without brackets)
<pre><code>
self.filed.mask = "{dddd}-{DDDD}-{WaWa}-{aaaa}"      \\ 19 characters  
self.filed.maskPlaceholder = "ABCD-EFGH-IJKL-MNOP"   \\ 19 characters

// Text in mask filed
// ABCD-EFGH-IJKL-MNOP
</code></pre>
</li>
</ul>
