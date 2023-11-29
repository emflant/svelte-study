<script>
    import { onMount } from 'svelte';
    import hljs from 'highlight.js';
    import 'highlight.js/styles/atom-one-dark.min.css';
    
    export let data;
    
    const code1 = '<div class="row"><span>Hello World!</span></div>';

    const code2 = `
    <div class="row">
        <span>Hello World!</span>
    </div>
    `;
    
    // onMount 의 기능발견!
    onMount(() => {
        hljs.highlightAll(); // 모든 코드 블록을 강조 표시
    });

</script>

<svelte:head>
    
</svelte:head>

<div><h2 class="my-5">Svelte에서 highlight.js 연동1</h2></div>

<pre>
    
</pre>

<div class="row">
    <div class="col-md-7">
        <h4>Code</h4>
        <pre><code class="language-html">{code1}</code></pre>
        <pre><code class="language-html">{code2}</code></pre>
        <pre><code class="language-csharp">{data.code03}</code></pre>
        
    </div>
    <div class="col-md-5">
        <div>
            
        </div>
    </div>
</div>
