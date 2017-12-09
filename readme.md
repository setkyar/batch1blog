@if($errors->any())
<div class="alert alert-danger">
    @foreach($errors->all() as $error)
        <p>{{ $error }}</p>
    @endforeach
</div>
@endif

$this->validate($request, [
    'title' => 'required',
    'description' => 'required'
]);

Session::flash('flash_message', 'Blog successfully added!');

@if(Session::has('flash_message'))
    <div class="alert alert-success">
        {{ Session::get('flash_message') }}
    </div>
@endif