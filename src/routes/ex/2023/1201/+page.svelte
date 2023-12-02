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
        // console.log(hljs.listLanguages())
        
    });
</script>

<svelte:head>
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/11.9.0/styles/atom-one-dark.min.css">
</svelte:head>

<div><h2 class="my-5">Svelte에서 highlight.js 에 언어정보 배지추가</h2></div>

<div class="row">
    <div class="col-lg-6">
        <h4>text-bg-warning 테마</h4>
        <div class="position-relative">
            <pre><code class="language-julia">{codeJulia}</code>
            </pre>
            <h6><span class="position-absolute top-0 end-0 badge text-bg-warning rounded-0 p-2">JAVA</span></h6>
        </div>

        <h4>text-bg-dark 테마</h4>
        <p>그런데 <code>text-bg-dark</code> 가 완벽한 black은 아니어서 <code>bootstrap.css</code> 파일을 수정했다.</p>
        <div class="position-relative">
            <pre><code class="language-julia">{codeJulia}</code>
            </pre>
            <h6><span class="position-absolute top-0 end-0 badge text-bg-dark rounded-0 p-2">JAVA</span></h6>
        </div>
    </div>
    <div class="col-lg-6">
    </div>
    
</div>