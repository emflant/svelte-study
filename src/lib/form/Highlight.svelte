<script>
    export let code;
    export let language;
</script>

<div class="position-relative">
    <pre><code class="language-{language} rounded-3">{code}</code>
    </pre>
    <h6><span class="position-absolute top-0 end-0 
        badge text-bg-warning rounded-3 rounded-bottom-0 rounded-start-0 py-2 px-2 text-uppercase">{language}</span></h6>
</div>