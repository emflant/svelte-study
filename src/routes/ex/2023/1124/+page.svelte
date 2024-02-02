<script>
    import { onMount } from 'svelte';

    import 'bootstrap-icons/font/bootstrap-icons.css'
    import HighlightPop from '$lib/form/HighlightPop.svelte';

    import hljs from 'highlight.js/lib/core';
    import xml from 'highlight.js/lib/languages/xml';
    import 'highlight.js/styles/atom-one-dark.min.css';

    hljs.registerLanguage('xml', xml);
    

    onMount(() => {
        hljs.highlightAll();
        const popoverTriggerList = document.querySelectorAll('[data-bs-toggle="popover"]')
        const popoverList = [...popoverTriggerList].map(popoverTriggerEl => new bootstrap.Popover(popoverTriggerEl))
    });

</script>
<div><h2 class="my-5">Svelte에서 Bootstrap Icons 사용하기 - 1.Package Manager</h2></div>

<div class="row">
    <div class="col-md-7">
        <h4>Code</h4>
        <HighlightPop code={codeHtml} language="html" />
    </div>
    <div class="col-md-5">
        <h4>Result</h4>
        <div>
            <i class="bi bi-amazon" style="font-size: 3rem;margin-right:0.3em"></i>
            <i class="bi bi-apple" style="font-size: 3rem;margin-right:0.3em"></i>
            <i class="bi bi-twitter" style="font-size: 3rem;margin-right:0.3em"></i>
            <i class="bi bi-instagram" style="font-size: 3rem;margin-right:0.3em; color: cornflowerblue;"></i>
        </div>
        
    </div>
</div>
