<script>
    import { onMount } from 'svelte';
    import HighlightPop from '$lib/form/HighlightPop.svelte';

    import hljs from 'highlight.js/lib/core';
    import typescript from 'highlight.js/lib/languages/typescript';
    import julia from 'highlight.js/lib/languages/julia';
    import go from 'highlight.js/lib/languages/go';
    import makefile from 'highlight.js/lib/languages/makefile';

    import 'highlight.js/styles/atom-one-dark.min.css';
    import 'bootstrap-icons/font/bootstrap-icons.css'

    // 필요한 언어만 가져다가 바인딩 한다.
    hljs.registerLanguage('go', go);
    hljs.registerLanguage('typescript', typescript);
    hljs.registerLanguage('julia', julia);
    hljs.registerLanguage('makefile', makefile);
    
    const codeGo =
`package main

import "fmt"

func main() {
    fmt.Println("Hello, 世界")
}`;

const codeJulia = 
`function f(x, y)
    x[1] = 42    # mutates x
    y = 7 + y    # new binding for y, no mutation
    return y
end`;

    const codeMakefile =
`# Makefile

BUILDDIR      = _build
EXTRAS       ?= $(BUILDDIR)/extras

.PHONY: main clean

main:
	@echo "Building main facility..."
	build_main $(BUILDDIR)

clean:
	rm -rf $(BUILDDIR)/*`;

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
    <div class="col-lg-6">
        <h4>불필요한 공백이 있는 경우</h4>
        <pre style="border:3px red solid">
            <code class="language-typescript">{codeTypescript}</code>
        </pre>
        <pre style="border:3px red solid">
            <code class="language-julia">{codeJulia}</code>
        </pre>
    </div>
    <div class="col-lg-6">
        <h4>불필요한 공백이 없는 경우</h4>
        <pre style="border:3px red solid"><code class="language-typescript">{codeTypescript}</code></pre>
        <pre style="border:3px red solid"><code class="language-julia">{codeJulia}</code></pre>
    </div>
</div>