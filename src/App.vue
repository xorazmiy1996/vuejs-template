<template>
  <nav class="sidebar close">
    <header>
      <div class="image-text">
        <span class="image">
          <img :src="logo"/>
        </span>
        <div class="text hider-text">
          <span class="name">CodingLab</span>
          <span class="professional"> Web developer</span>
        </div>
      </div>
      <i class="bx bx-chevron-right toggle"></i>
    </header>
    <div class="menu-bar">
      <div class="menu">
        <li class="search-box">
          <i class="bx bx-search icon"></i>
          <input type="search"
                 placeholder="Search..."/>

        </li>
        <ul class="menu-link">
          <li class="nav-link">
            <router-link to="/about">
              <i class="bx bx-home icon"></i>
              <span class="text nav-text">Dashboard</span>
            </router-link>
          </li>
          <li class="nav-link">
            <router-link to="#">

              <i class="bx bx-bar-chart-alt-2 icon"></i>
              <span class="text nav-text">Revenue</span>
            </router-link>
          </li>
          <li class="nav-link">
            <router-link to="#">
              <i class="bx bx-bell icon"></i>
              <span class="text nav-text">Notification</span>
            </router-link>
          </li>
          <li class="nav-link">
            <router-link to="#">
              <i class="bx bx-pie-chart-alt-2 icon"></i>
              <span class="text nav-text">Analytics</span>
            </router-link>
          </li>
          <li class="nav-link">
            <router-link to="#">
              <i class="bx bx-heart icon"></i>
              <span class="text nav-text">Like</span>
            </router-link>
          </li>
          <li class="nav-link">
            <router-link to="#">
              <i class="bx bx-wallet icon"></i>
              <span class="text nav-text">Wallets</span>
            </router-link>
          </li>
        </ul>
      </div>

      <div class="bottom-content">
        <li class="">
          <router-link to="#">
            <i class="bx bx-log-out icon"></i>
            <span class="text nav-text">Logout</span>
          </router-link>
        </li>
        <li class="mode">
          <div class="moon-sun">
            <i class="bx bx-moon icon moon"></i>
            <i class="bx bx-sun icon sun"></i>
          </div>
          <span class="mode-text text"> Dark Mode</span>
          <div class="toggle-switch">
            <span class="switch"></span>
          </div>
        </li>
      </div>

    </div>
  </nav>
  <section class="home">
    <div class="text">Dashboard</div>
  </section>
  <router-view/>
</template>


<script setup>
import logo from "@/logo/codinglab.png";





</script>


<style scoped>


/*===== Sidebar=====*/

.sidebar {
  position: fixed;
  top: 0;
  left: 0;
  height: 100%;
  width: 250px;
  padding: 10px 14px;
  background: var(--sidebar-color);
  transition: var(--tran-05);
  z-index: 1;
}
.sidebar.close {
  width: 88px;
}

/*===== Resuable CSS=====*/
.sidebar .text {
  font-size: 16px;
  font-weight: 500;
  color: var(--text-color);
  transition: var(--tran-04);
  white-space: nowrap;
  opacity: 1;
}

.sidebar.close .text {
  opacity: 0;
}

.sidebar header {
  position: relative;
}

.sidebar .image {
  min-width: 60px;
  display: flex;
  align-items: center;

}

.sidebar li {
  list-style: none;
  height: 50px;
  margin-top: 10px;
  display: flex;
  align-items: center;
}

.sidebar li .icon {
  font-size: 20px;
  min-width: 60px;
  display: flex;
  align-items: center;
  justify-content: center;

}

.sidebar li .icon,
.sidebar li .text {
  color: var(--text-color);
}

.sidebar li a {
  text-decoration: none;
  height: 100%;
  width: 100%;
  display: flex;
  align-items: center;
  border-radius: 6px;
  transition: var(--tran-03);

}

.sidebar .image-text img {
  width: 40px;
  border-radius: 6px;

}

.sidebar header .image-text {
  display: flex;
  align-items: center;
}

header .image-text .hider-text {
  display: flex;
  flex-direction: column;
}

.hider-text .name {
  font-weight: 600;
}

.hider-text .professional {
  margin-top: -2px;
}

.sidebar header .toggle {
  position: absolute;
  top: 50%;
  right: -25px;
  transform:translateY(-50%) rotate(180deg) ;
  width: 25px;
  height: 25px;
  background: var(--primary-color);
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50px;
  font-size: 22px;
  color: var(--sidebar-color);
  transition: var(--tran-05);

}
  .sidebar.close header .toggle{
     transform: translateY(-50%);


  }
   body.dark .sidebar header .toggle{
     transform: rotate(180deg);
    color: var(--text-color);
  }


.sidebar .search-box {
   border-radius: 5px;
  background: var(--primary-color-light);
}

.search-box input {
  font-weight: 500;
  font-size: 18px;

  height: 100%;
  width: 100%;
  border: none;
  outline: none;
  background: var(--primary-color-light);
  border-radius: 6px;

}

.sidebar li a:hover {
  background: var(--primary-color);
}

.sidebar li a:hover .icon,
.sidebar li a:hover .text {
  color: var(--sidebar-color);
}

body.dark .sidebar li a:hover .icon,
body.dark .sidebar li a:hover .text {
  color: var(--text-color);
}

.sidebar .menu-bar {
  height: calc(100% - 50px);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

.menu-bar .mode {
  position: relative;
  border-radius: 5px;
  background: var(--primary-color-light);
}

.menu-bar .mode .moon-sun {
  width: 60px;
  height: 50px;
  display: flex;
  align-items: center;

}

.menu-bar .mode i {
  transition: var(--tran-03);
  position: absolute;
}

.menu-bar .mode i.sun {
  opacity: 0;

}
body.dark .menu-bar .mode i.sun {
  opacity: 1;
}
body.dark .menu-bar .mode i.moon {
  opacity: 0;
}

.menu-bar .mode .toggle-switch {
  position: absolute;
  right  : 0px;

  display: flex;
  height: 100%;
  align-items: center;
  justify-content: center;
  min-width: 60px;
  cursor: pointer;


}

.toggle-switch .switch {
  border-radius: 25px;
  position: relative;

  height: 22px;
  width: 44px;
  background: var(--toggle-color);
}

.switch::before {
  content: "";
  position: absolute;
  border-radius: 50px;
  height: 15px;
  width: 15px;
  transform: translateY(3px);
  left: 5px;
  background: var(--sidebar-color);
  transition: var(--tran-03);
}

body.dark .switch::before {
  left: 20px;
}

.home{
  position: relative;
  left: 250px;
  height: 100vh;
  width: calc(100% - 250px);
  background: var(--body-color);
  transition: var(--tran-05);
}
.sidebar.close ~ .home{
  left: 88px;
  width: calc(100% - 88px);

}


</style>
