<template>

<nav class="navbar navbar-expand-lg bg-success navbar-dark">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">Reports application</a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <router-link to = "/" class="nav-link active" aria-current="page" href="#">Report sales </router-link>
        </li>
        <li class="nav-item">
          <router-link to="/create" class="nav-link" href="#">Create</router-link>
        </li>
        <li class="nav-item">
          <router-link to="/reporte" class="nav-link" href="#">ReportView</router-link>
        </li>
      </ul>
    </div>
  </div>
</nav>

<div class="container-fluid mt-3">
  <router-view/>
</div>
</template>


