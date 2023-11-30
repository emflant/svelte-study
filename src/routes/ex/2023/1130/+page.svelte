<script>
    import { onMount } from 'svelte';

    // hljs.registerLanguage('xml', xml);
    
    const code1 = '<div class="row"><span>Hello World!</span></div>';

    const code2 = 
`<div class="row">
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


    onMount(() => {
        // hljs.registerLanguage('julia', julia);
        hljs.highlightAll();
        console.log(hljs.listLanguages())
        
    });
</script>

<svelte:head>
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/atom-one-dark.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/highlight.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/languages/julia.min.js"></script>
</svelte:head>

<div><h2 class="my-5">Svelte에서 highlight.js 연동 -1130</h2></div>

<div class="row">
    <div class="col-lg-6">
        <h4>Code</h4>
        <pre><code class="language-go">{code3}</code></pre>
        <pre><code class="language-html">{code2}</code></pre>
        <pre><code class="language-julia">{codeJulia}</code></pre>
    </div>
    <div class="col-lg-6"></div>
</div>