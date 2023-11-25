<script>
    import 'bootstrap-icons/font/bootstrap-icons.css'
</script>
<div><h2 class="my-5">Svelte에서 Bootstrap Icons 사용하기 - 1.Package Manager</h2></div>

<div class="row">
    <div class="col-md-7">
        <h4>Code</h4>
        <textarea class="form-control" id="exampleFormControlTextarea1" rows="15" readonly
        style="font-family:monospace;">
&lt;script&gt;
    import 'bootstrap-icons/font/bootstrap-icons.css'
&lt;/script&gt;

<i class="bi bi-amazon"></i>
<i class="bi bi-apple"></i>
<i class="bi bi-twitter"></i>
<i class="bi bi-instagram" style="color: cornflowerblue;"></i>
        </textarea>
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
