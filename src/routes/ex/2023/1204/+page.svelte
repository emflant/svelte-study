<script>
    import { onMount } from 'svelte';

    import hljs from 'highlight.js/lib/core';
    import typescript from 'highlight.js/lib/languages/typescript';
    import julia from 'highlight.js/lib/languages/julia';
    import xml from 'highlight.js/lib/languages/xml';

    import 'highlight.js/styles/atom-one-dark.min.css';
    import 'bootstrap-icons/font/bootstrap-icons.css'

    // 필요한 언어만 가져다가 바인딩 한다.
    hljs.registerLanguage('typescript', typescript);
    hljs.registerLanguage('julia', julia);
    hljs.registerLanguage('xml', xml);
    
const codeJulia = 
`function f(x, y)
    x[1] = 42    # mutates x
    y = 7 + y    # new binding for y, no mutation
    return y
end`;

    const codeTypescript = 
`class MyClass {
  public static myValue: string;
  constructor(init: string) {
    this.myValue = init;
  }
}
import fs = require("fs");
module MyModule {
  export interface MyInterface extends Other {
    myProperty: any;
  }
}
declare magicNumber number;
myArray.forEach(() => { }); // fat arrow syntax`;

    onMount(() => {
        hljs.highlightAll();
        const popoverTriggerList = document.querySelectorAll('[data-bs-toggle="popover"]')
        const popoverList = [...popoverTriggerList].map(popoverTriggerEl => new bootstrap.Popover(popoverTriggerEl))
        // const popover = new bootstrap.Popover('.popover-dismiss', {
        //     trigger: 'focus'
        // })
    });

</script>

<div><h2 class="my-5">pre 태그 공백</h2></div>

<div class="row">
    <div class="col-lg-6 mb-5">
        <h4 class="mb-4">불필요한 공백이 있는 경우</h4>
        <p>pre 태그를 아래와 같이 이쁘게 줄바꿈을 넣어가며 정리하는 순간,</p>
        <pre><code class="language-xml">&lt;pre style=&quot;border:3px red solid&quot;&gt;
    &lt;code class=&quot;language-typescript&quot;&gt;codeTypescript&lt;/code&gt;
&lt;/pre&gt;
&lt;pre style=&quot;border:3px red solid&quot;&gt;
    &lt;code class=&quot;language-julia&quot;&gt;codeJulia&lt;/code&gt;
&lt;/pre&gt;</code></pre>
        <p>결과는 아래와 같다. 불필요한 공간이 생기게 된다.</p>
        <pre style="border:3px red solid">
            <code class="language-typescript">{codeTypescript}</code>
        </pre>
        <pre style="border:3px red solid">
            <code class="language-julia">{codeJulia}</code>
        </pre>
    </div>
    <div class="col-lg-6 mb-5">
        <h4 class="mb-4">불필요한 공백이 없는 경우</h4>
        <p>pre 태그내에서는 아래와 같이 공백없이 코딩해야,</p>
        <pre><code>&lt;pre style=&quot;border:3px red solid&quot;&gt;&lt;code class=&quot;language-typescript&quot;&gt;codeTypescript&lt;/code&gt;&lt;/pre&gt;
&lt;pre style=&quot;border:3px red solid&quot;&gt;&lt;code class=&quot;language-julia&quot;&gt;codeJulia&lt;/code&gt;&lt;/pre&gt;</code></pre>
        <p>쓸데없는 공간이 생기지 않는다.</p>
        <pre style="border:3px red solid"><code class="language-typescript">{codeTypescript}</code></pre>
        <pre style="border:3px red solid"><code class="language-julia">{codeJulia}</code></pre>
    </div>
</div>