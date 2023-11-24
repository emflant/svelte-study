<script>
    import { validateForm } from '$lib/js/formValidation.js'
</script>

<form method="POST" class="needs-validation" novalidate on:submit={validateForm}>
    <slot/>
</form>