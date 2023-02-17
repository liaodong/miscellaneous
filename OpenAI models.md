<h1><strong>模型</strong></h1>
<h2><strong>概述</strong></h2>
<p class="p">OpenAI API 由一系列具有不同功能和价位的模型提供支持。您还可以通过<a href="https://platform.openai.com/docs/guides/fine-tuning" rel="noopener"><span style="font-family: helvetica;">微调</span></a>为您的特定用例自定义我们的基本模型。</p>
<table border="0" cellspacing="0">
<tbody>
<tr>
<td valign="bottom" width="128">
<p><strong>模型</strong></p>
</td>
<td valign="bottom" width="656">
<p><strong>描述</strong></p>
</td>
</tr>
<tr>
<td valign="top" nowrap="nowrap" width="128">
<p><a href="https://platform.openai.com/docs/models/gpt-3" rel="noopener">GPT-3</a></p>
</td>
<td valign="top" width="656">
<p>一组可以理解和生成自然语言的模型</p>
</td>
</tr>
<tr>
<td valign="top" nowrap="nowrap" width="128">
<p><a href="https://platform.openai.com/docs/models/codex" rel="noopener">Codex</a></p>
<p><strong>Limited beta</strong></p>
<p><strong>&nbsp;</strong></p>
</td>
<td valign="top" width="656">
<p>一组可以理解和生成代码的模型，包括将自然语言转换为代码</p>
</td>
</tr>
<tr>
<td valign="top" nowrap="nowrap" width="128">
<p><a href="https://platform.openai.com/docs/models/content-filter" rel="noopener">Content filter</a></p>
</td>
<td valign="top" width="656">
<p>可以检测文本是否敏感或不安全的微调模型</p>
</td>
</tr>
</tbody>
</table>
<h2><strong>GPT-3</strong></h2>

<p class="p">&nbsp;GPT-3 模型可以理解和生成自然语言。我们提供四种主要模型，它们具有不同的能力（适用于不同的任务）。达芬奇是最有能力的模型，而艾达是最快的。</p>
<table border="0" cellspacing="0">
<tbody>
<tr>
<td valign="bottom">
<p><strong>最新</strong><strong>模型</strong></p>
</td>
<td valign="bottom">
<p><strong>描述</strong></p>
</td>
<td valign="bottom">
<p><strong>最大请求数</strong></p>
</td>
<td valign="bottom">
<p><strong>训练数据</strong></p>
</td>
</tr>
<tr>
<td valign="top" nowrap="nowrap">
<p>text-davinci-003</p>
</td>
<td valign="top">
<p><span style="font-family: 宋体;">功能最强大的</span> GPT-3 模型。可以完成其他模型可以完成的任何任务，通常具有更高的质量、更长的输出和更好的指令遵循。还支持在文本中插入补全。</p>
</td>
<td valign="top">
<p>4，000 tokens</p>
</td>
<td valign="top">
<p><span style="font-family: 宋体;">截至</span>2021年6月</p>
</td>
</tr>
<tr>
<td valign="top" nowrap="nowrap">
<p>text-curie-001</p>
</td>
<td valign="top">
<p>非常有能力，但比达芬奇更快，成本更低。</p>
</td>
<td valign="top">
<p>2，048 tokens</p>
</td>
<td valign="top">
<p><span style="font-family: 宋体;">截至</span>2019年10月</p>
</td>
</tr>
<tr>
<td valign="top" nowrap="nowrap">
<p>text-babbage-001</p>
</td>
<td valign="top">
<p>能够完成简单的任务，速度非常快，成本更低。</p>
</td>
<td valign="top">
<p>2，048 tokens</p>
</td>
<td valign="top">
<p><span style="font-family: 宋体;">截至</span>2019年10月</p>
</td>
</tr>
<tr>
<td valign="top" nowrap="nowrap">
<p>text-ada-001</p>
</td>
<td valign="top">
<p><span style="font-family: 宋体;">能够完成非常简单的任务，通常是</span> GPT-3 系列中最快的模型，成本最低。</p>
</td>
<td valign="top">
<p>2，048 tokens</p>
</td>
<td valign="top">
<p><span style="font-family: 宋体;">截至</span>2019年10月</p>
</td>
</tr>
</tbody>
</table>
<p class="p">虽然达芬奇（davinci）通常是最有能力的模型，但其他模型同样也可以非常出色地执行某些任务，具有显着的速度或<a href="https://openai.com/api/pricing" rel="noopener"><span style="font-family: helvetica;">成本优势</span></a>。例如，居里（curie）<span style="font-family: helvetica;">可以执行许多与达芬奇相同的任务，但速度更快，成本仅为达芬奇的</span>1/10。</p>
<p class="p">我们建议在实验时使用达芬奇，因为它会产生最好的结果。一旦你开始工作，我们鼓励尝试其他模型，看看你是否能以更低的延迟获得相同的结果。您还可以通过在特定任务上微调其他模型来提高它们的性能。</p>
<p>&nbsp;</p>
<p>模型的功能规格说明</p>
<p class="p"><span style="font-family: helvetica;">主要的</span> GPT-3 模型旨在与<a href="https://platform.openai.com/docs/guides/completion" rel="noopener"><span style="font-family: helvetica;">文本完成</span></a>终结点一起使用。我们还提供专门用于其他端点的模型。</p>
<p class="p"><span style="font-family: helvetica;">我们的</span> GPT-3 型号的旧版本可作为,,,和提供。这些旨在与我们的<a href="https://platform.openai.com/docs/guides/fine-tuning" rel="noopener"><span style="font-family: helvetica;">微调</span></a>端点一起使用。<a href="https://help.openai.com/en/articles/5832130" rel="noopener"><span style="font-family: helvetica;">了解更多</span></a>。davincicuriebabbageada</p>
<p class="p">我们用于<a href="https://platform.openai.com/docs/guides/embeddings" rel="noopener"><span style="font-family: helvetica;">创建嵌入</span></a>和<a href="https://platform.openai.com/docs/guides/completion/editing-text" rel="noopener"><span style="font-family: helvetica;">编辑文本</span></a>的端点使用自己的专用模型集。</p>
<p>&nbsp;</p>
<hr align="center" size="2" width="506">

<h3><strong>达芬奇</strong></h3>
<p>&nbsp;</p>
<p class="p">Davinci是最有能力的模型系列，可以执行其他模型可以执行的任何任务，而且通常只需较少的指令。对于需要对内容有充分理解的应用程序，例如针对特定受众的摘要和创意内容生成，Davinci 将产生最佳结果。这些增加的功能需要更多的计算资源，因此 Davinci 每次 API 调用的成本更高，并且不如其他模型快。</p>
<p class="p">达芬奇的另一个亮点是理解文本的意图。达芬奇相当擅长解决多种逻辑问题，解释人物的动机。达芬奇已经能够解决一些涉及因果关系的最具挑战性的人工智能问题。</p>
<p class="p">擅长：<strong>复杂意图、因果关系、观众总结</strong></p>
<p>&nbsp;</p>
<h3><strong>居里</strong></h3>
<p>&nbsp;</p>
<p class="p">居里非常强大，但速度非常快。虽然达芬奇在分析复杂文本方面更强，但居里非常有能力完成许多细微的任务，如情感分类和总结。居里还非常擅长回答问题和执行问答，并作为一般服务聊天机器人。</p>
<p class="p">擅长：<strong>语言翻译、复杂分类、文本情感、总结</strong></p>
<p>&nbsp;</p>
<h3><strong>巴贝奇</strong></h3>
<p>&nbsp;</p>
<p class="p">巴贝奇可以执行简单的任务，比如简单的分类。在语义搜索排名文档与搜索查询的匹配程度方面，它也非常有能力。</p>
<p class="p">擅长：<strong>中等分类、语义搜索分类</strong></p>
<p>&nbsp;</p>
<h3><strong>阿达</strong></h3>
<p>&nbsp;</p>
<p class="p">Ada 通常是最快的模型，可以执行解析文本、地址更正和某些不需要太多细微差别的分类任务等任务。Ada 的性能通常可以通过提供更多上下文来提高。</p>
<p class="p">擅长：<strong>解析文本、简单分类、地址更正、关键词</strong></p>
<p class="p"><span style="font-family: helvetica;">注意：由像</span>Ada这样的更快模型执行的任何任务都可以由像Curie或Davinci这样的更强大的模型执行。</p>
<p>OpenAI模型是非确定性的，这意味着相同的输入可以产生不同的输出。将<a rel="noopener"><span style="font-family: helvetica;">温度</span></a><span style="font-family: helvetica;">设置为</span> 0 将使输出大部分具有确定性，但可能会保留少量可变性。</p>
<p>&nbsp;</p>

<h2><strong><span style="font-family: 宋体;"><strong>Codex</strong></span><span style="font-family: 宋体;"> </span></strong></h2>
<p><strong>限量测试版</strong></p>
<p class="p">Codex 模型是我们的 GPT-3 模型的后代，可以理解和生成代码。他们的训练数据包含自然语言和来自GitHub的数十亿行公共代码。<a href="https://help.openai.com/en/articles/5480054" rel="noopener"><span style="font-family: helvetica;">了解更多</span></a>。</p>
<p class="p"><span style="font-family: helvetica;">他们最擅长</span>Python，精通十几种语言，包括JavaScript，Go，Perl，PHP，Ruby，Swift，TypeScript，SQL甚至Shell。</p>
<p class="p">我们目前提供两种法典模式：</p>
<table border="0" cellspacing="0">
<tbody>
<tr>
<td valign="bottom">
<p><strong>最新型号</strong></p>
</td>
<td valign="bottom">
<p><strong>描述</strong></p>
</td>
<td valign="bottom">
<p><strong>最大请求数</strong></p>
</td>
<td valign="bottom">
<p><strong>训练数据</strong></p>
</td>
</tr>
<tr>
<td valign="top" nowrap="nowrap">
<p><span style="">code-davinci-002</p>
</td>
<td valign="top">
<p>最有能力的法典模型。特别擅长将自然语言翻译成代码。除了完成代码外，还支持在代码中<a href="https://platform.openai.com/docs/guides/code/inserting-code" rel="noopener"><span style="font-family: 宋体;">插入</span></a>完成。</p>
</td>
<td valign="top">
<p>8，000 代币</p>
</td>
<td valign="top">
<p><span style="font-family: 宋体;">截至</span>2021年&lt;&gt;月</p>
</td>
</tr>
<tr>
<td valign="top" nowrap="nowrap"
<p><span style="">code-cushman-001</p>
</td>
<td valign="top">
<p>几乎和达芬奇手抄本一样强大，但速度略快。这种速度优势可能使其更适合实时应用程序。</p>
</td>
<td valign="top">
<p><span style="font-family: 宋体;">最多</span> 2，048 个代币</p>
</td>
<td valign="top">
<p>&nbsp;</p>
</td>
</tr>
</tbody>
</table>
<p class="p">有关更多信息，请访问我们的<a href="https://platform.openai.com/docs/guides/code" rel="noopener">Codex 使用</a>指南。</p>

<hr align="center" size="2" width="506">

<h2><strong>Content filter</strong></h2>

<p><strong>我们建议使用新的</strong><a href="https://platform.openai.com/docs/guides/moderation" rel="noopener"><strong><span style="font-family: helvetica;">moderation endpoint</span></strong></a><strong>，而不是Content filter模型。</strong></p>
<p class="p"><span style="font-family: helvetica;">该筛选器旨在检测来自</span> API 的敏感或不安全的生成文本。它目前处于测试模式，有三种将文本分类为、或的方法。过滤器会出错，我们目前已经将其构建为谨慎行事，从而导致更高的误报率。safesensitiveunsafe</p>
<h3><strong>标签说明</strong></h3>
<ul>
<li><strong>0</strong>-文本是安全的。</li>
<li><strong>1</strong>-此文本是敏感的。这意味着文本可能是在谈论一个敏感的话题，一些政治、宗教的东西，或者谈论一个受保护的阶级，如种族或国籍。</li>
<li><strong>2</strong>-此文本不安全。这意味着文本包含亵渎性语言、偏见或仇恨语言、可能是 NSFW 的内容，或以有害方式描绘某些群体/人群的文本。</li>
</ul>


