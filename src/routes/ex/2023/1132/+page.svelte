<script>
    import { onMount } from 'svelte';
    import hljs from 'highlight.js/lib/core';
    import javascript from 'highlight.js/lib/languages/javascript';
    import julia from 'highlight.js/lib/languages/julia';
    import go from 'highlight.js/lib/languages/go';

    // 필요한 언어만 가져다가 바인딩 한다.
    hljs.registerLanguage('go', go);
    hljs.registerLanguage('javascript', javascript);
    hljs.registerLanguage('julia', julia);
    
    const code1 = '<div class="row"><span>Hello World!</span></div>';

    const code2 = 
`<!-- 여기는 적용되지 않는다. -->
<div class="row">
    <span>Hello World!</span>
</div>`;

const code3 =
`package main

import "fmt"

func main() {
	fmt.Println("Hello, 世界")
}
`;

const codeJulia = 
`function f(x, y)
    x[1] = 42    # mutates x
    y = 7 + y    # new binding for y, no mutation
    return y
end
`

const codeImport = 
`// 정말 필요한 언어만 import 하고 싶다면,  
import hljs from 'highlight.js/lib/core';
import javascript from 'highlight.js/lib/languages/javascript';
import julia from 'highlight.js/lib/languages/julia';
import go from 'highlight.js/lib/languages/go';

hljs.registerLanguage('javascript', javascript);
hljs.registerLanguage('julia', julia);
hljs.registerLanguage('go', go);
`;


    onMount(() => {
        // hljs.registerLanguage('julia', julia);
        hljs.highlightAll();
        // console.log(hljs.listLanguages())
        
    });
</script>

<svelte:head>
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/atom-one-dark.min.css">
</svelte:head>

<div><h2 class="my-5">Svelte에서 highlight.js 연동 -1132</h2></div>

<div class="row">
    <div class="col">
        <h4>Code { hljs.listLanguages().length }개 언어</h4>
        <pre><code class="language-javascript">{codeImport}</code></pre>
        <pre><code class="language-go">{code3}</code></pre>
        <pre><code class="language-html">{code2}</code></pre>
        <pre><code class="language-julia">{codeJulia}</code></pre>
    </div>
</div>