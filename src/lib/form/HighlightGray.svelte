<script>
    export let code;
    export let language;
</script>
<div class="position-relative m-0">
    <pre><code class="language-{language} rounded-3">{code}</code></pre>
    <span class="position-absolute top-0 end-0 
        badge rounded-3 py-2 px-2 text-uppercase" 
        style="color:#C0C0C0">{language}</span>
    <!-- <span class="position-absolute top-50 end-0"><i class="bi bi-copy" 
        style="font-size: 1rem;margin-right:0.3em; color: white;"></i></span> -->
</div>
