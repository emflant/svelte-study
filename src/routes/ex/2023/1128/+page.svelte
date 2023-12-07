<script>
    import { onMount } from 'svelte';
    
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
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/atom-one-dark.min.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/highlight.min.js"></script>
    <!-- and it's easy to individually load additional languages -->
    <!-- <script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/languages/go.min.js"></script> -->
</svelte:head>

<div><h2 class="my-5">Svelte에서 highlight.js 연동-1128</h2></div>

<div class="row">
    <div class="col">
        <pre><code class="language-html">{code1}</code></pre>
        <pre><code class="language-html">{code2}</code></pre>
        <!-- <pre><code class="language-csharp">{data.code03}</code></pre> -->
    </div>
</div>