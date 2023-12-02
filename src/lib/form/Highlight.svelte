<script>
    export let code;
    export let language;
</script>

<div class="position-relative">
    <pre><code class="language-{language} rounded-2">{code}</code>
    </pre>
    <h6><span class="position-absolute top-0 end-0 
        badge text-bg-warning rounded-1 p-2 text-uppercase">{language}</span></h6>
</div>