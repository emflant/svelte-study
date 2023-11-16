<script>

    import InputText from '$lib/form/InputText.svelte'
    import Select from '$lib/form/Select.svelte'
    import Form from '$lib/form/Form.svelte'
    // import { validateForm, resetAllForm } from '$lib/js/formValidation.js'

    let contents = {};
    let cdGender = [ { id : null, name : '-'}, { id : 'M', name : '남' }, { id : 'F', name : '여'}];
</script>

<svelte:head>
	<title>ex12</title>
	<meta name="description" content="About this app" />
</svelte:head>

<div><h2 class="mt-5">exmple111</h2></div>
<div class="row">
	<div class="col">
        <div class="row">
            <div class="col-md">
                <label for="exampleFormControlTextarea1" class="form-label">결과</label>
                <textarea class="form-control" id="exampleFormControlTextarea1" rows="5">{JSON.stringify(contents, null, 2)}</textarea>
            </div>
            <div class="col">
                <Form>
                    <div class="mb-2">
                        <InputText id = "name" title="이름" bind:val={contents.name} />
                    </div>
                    <div class="mb-2">
                        <Select id="gender" bind:val={contents.gender} cdSet={cdGender} validateYn={true}/>
                    </div>
                    <button class="btn btn-primary" type="submit">submit</button>
                </Form>
            </div>
            
        </div>
    </div>
</div>