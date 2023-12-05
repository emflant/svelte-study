<script>
    import { onMount } from 'svelte';
    import HighlightGray from '$lib/form/HighlightGray.svelte';
    import hljs from 'highlight.js/lib/core';
    import javascript from 'highlight.js/lib/languages/javascript';
    import julia from 'highlight.js/lib/languages/julia';
    import go from 'highlight.js/lib/languages/go';
    import 'highlight.js/styles/atom-one-dark.min.css';
    import 'bootstrap-icons/font/bootstrap-icons.css'

    // 필요한 언어만 가져다가 바인딩 한다.
    hljs.registerLanguage('go', go);
    hljs.registerLanguage('javascript', javascript);
    hljs.registerLanguage('julia', julia);
    
    const codeGo =
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
        hljs.highlightAll();
    });

</script>

<div><h2 class="my-5">Svelte에서 highlight.js 에 언어정보 배지추가</h2></div>

<div class="row">
    
    <div class="col-lg-6">
        <h4>text-bg-warning 테마</h4>
        <p>warning 테마도 어울리는 편 같다. 모서리마다 약간 라운드 처리를 하니 조금 더 부드러워 보인다.</p>
        <HighlightGray code={codeGo} language="go" />
    </div>
    <div class="col-lg-6">
        <h4>text-bg-warning 테마</h4>
        <p>warning 테마도 어울리는 편 같다. 모서리마다 약간 라운드 처리를 하니 조금 더 부드러워 보인다.</p>
        <HighlightGray code={codeGo} language="go" />
    </div>
</div>