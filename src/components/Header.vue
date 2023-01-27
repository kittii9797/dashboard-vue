<template>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container py-1">
    <div>
      <a class="navbar-brand px-3" href="#">Logo</a>
    </div>  
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0 d-flex justify-content-start">
          <li class="nav-item px-3">
            <a class="nav-link active" aria-current="page" href="#">Home</a>
          </li>
          <li class="nav-item px-3">
            <a class="nav-link" href="#">Link</a>
          </li>
          <li class="nav-item px-3">
            <a class="nav-link" href="#">Show</a>
          </li>
          <li class="nav-item dropdown px-3">
            <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
              Dropdown
            </a>
            <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
              <li><a class="dropdown-item" href="#">Action</a></li>
              <li><a class="dropdown-item" href="#">Another action</a></li>
              <li><hr class="dropdown-divider"></li>
              <li><a class="dropdown-item" href="#">Something else here</a></li>
            </ul>
          </li>
        </ul>
        <div class="d-flex">
          <div class="searchbar">
                <input class="search_input" type="text" name="" placeholder="Search...">
                <a href="#" class="search_icon"><i class="bi bi-search"></i></a>
            </div>
        </div>
      </div>
    </div>
  </nav>
</template>


<style lang="scss">
@import url('https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.3/font/bootstrap-icons.css');

.searchbar {
	margin-bottom: auto;
	margin-top: auto;
	height: 50px;
	background-color: #353b48;
	border-radius: 30px;
	padding: 5px;
}

.search_input {
	color: white;
	border: 0;
	outline: 0;
	background: none;
	width: 0;
	caret-color: transparent;
	line-height: 40px;
	transition: width 0.4s linear;
}

.searchbar > .search_input {
	padding: 0 10px;
	width: auto;
	caret-color: rgb(44, 44, 44);
	transition: width 0.4s linear;
}

.searchbar > .search_icon {
	background: white;
	color: rgb(44, 44, 44);
}

.search_icon {
	height: 40px;
	width: 40px;
	float: right;
	display: flex;
	justify-content: center;
	align-items: center;
	border-radius: 50%;
	text-decoration: none;
	position: relative;
}
</style>