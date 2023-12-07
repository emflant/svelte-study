<script>
    import { onMount } from 'svelte';
    import hljs from 'highlight.js';
    import 'highlight.js/styles/atom-one-dark.min.css';
    
    export let data;
    
    const code1 = '<div class="row"><span>Hello World!</span></div>';

    const code2 = 
`<div class="row">
    <span>Hello World!</span>
</div>`;

    onMount(() => {
        hljs.highlightAll(); // 모든 코드 블록을 강조 표시        
    });

</script>

<svelte:head>
    
</svelte:head>

<div><h2 class="my-5">Svelte에서 highlight.js 연동 - npm 설치버전</h2></div>

<div class="row">
    <div class="col">
        <pre><code class="language-html">{code1}</code></pre>
        <pre><code class="language-html">{code2}</code></pre>
        <pre><code class="language-csharp">{data.code03}</code></pre>
    </div>
</div>

