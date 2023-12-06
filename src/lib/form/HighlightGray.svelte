<script>
    export let code;
    export let language;

    function aa(){
        navigator.clipboard.writeText(code);
    }
</script>
<div class="position-relative m-0">
    <pre><code class="language-{language} rounded-3">{code}</code></pre>
    <span class="position-absolute top-0 end-0 
        badge rounded-3 py-2 px-2 text-uppercase" 
        style="color:#C0C0C0;margin-right: 0em;margin-top:0em">{language}</span>
    <button class="btn p-0 position-absolute bottom-0 end-0" 
        style="margin-right: 0.4em;margin-bottom: 0.3em;"
        data-bs-toggle="popover" data-bs-placement="top" data-bs-content="Copied!"
        on:click={aa}>
        <i class="bi bi-copy" 
        style="font-size: 1rem;color: #C0C0C0;-webkit-text-stroke-width:0.04em"></i></button>
</div>
