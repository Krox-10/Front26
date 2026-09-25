<script>
    import logo from '$lib/assets/cul.png';
</script>

<nav class="navbar navbar-expand-lg bg-white border-bottom shadow-sm sticky-top">
    <div class="container-fluid px-4">

        <!-- LOGO + NOMBRE -->
        <a class="navbar-brand d-flex align-items-center gap-3" href="/inicio">

            <img
                src={logo}
                alt="Logo CUL"
                width="48"
                height="48"
                style="object-fit: contain;"
            />

            <div class="d-none d-sm-block">
                <div class="fw-bold titulo-navbar">
                    Gestión de Semilleros
                </div>

                <small class="text-secondary">
                    CUL
                </small>
            </div>

        </a>


        <!-- BOTÓN MÓVIL -->
        <button
            class="navbar-toggler"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarPrincipal"
            aria-controls="navbarPrincipal"
            aria-expanded="false"
            aria-label="Mostrar navegación"
        >
            <span class="navbar-toggler-icon"></span>
        </button>


        <!-- MENÚ -->
        <div class="collapse navbar-collapse" id="navbarPrincipal">

            <ul class="navbar-nav mx-auto mb-2 mb-lg-0">

                <li class="nav-item">
                    <a class="nav-link" href="/inicio">
                        <i class="bi bi-house-door me-1"></i>
                        Inicio
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link" href="/eventos">
                        <i class="bi bi-calendar-event me-1"></i>
                        Eventos
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link" href="/Estudiantes">
                        <i class="bi bi-people me-1"></i>
                        Estudiantes
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link" href="/semilleros">
                        <i class="bi bi-mortarboard me-1"></i>
                        Semilleros
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link" href="/proyectos">
                        <i class="bi bi-folder2-open me-1"></i>
                        Proyectos
                    </a>
                </li>

                <li class="nav-item">
                    <a class="nav-link" href="/productos">
                        <i class="bi bi-file-earmark-text me-1"></i>
                        Productos
                    </a>
                </li>

            </ul>


            <!-- USUARIO -->
            <div class="dropdown">

                <button
                    class="btn usuario-btn dropdown-toggle d-flex align-items-center gap-2"
                    type="button"
                    data-bs-toggle="dropdown"
                    aria-expanded="false"
                >

                    <span class="usuario-icono">
                        <i class="bi bi-person-fill"></i>
                    </span>

                    <span class="fw-semibold">
                        Usuario
                    </span>

                </button>

                <ul class="dropdown-menu dropdown-menu-end shadow">

                    <li>
                        <a class="dropdown-item" href="/perfil">
                            <i class="bi bi-person me-2"></i>
                            Mi perfil
                        </a>
                    </li>

                    <li>
                        <a class="dropdown-item" href="/configuracion">
                            <i class="bi bi-gear me-2"></i>
                            Configuración
                        </a>
                    </li>

                    <li>
                        <hr class="dropdown-divider">
                    </li>

                    <li>
                        <a class="dropdown-item text-danger" href="/">
                            <i class="bi bi-box-arrow-right me-2"></i>
                            Cerrar sesión
                        </a>
                    </li>

                </ul>

            </div>

        </div>

    </div>
</nav>


<style>
    .titulo-navbar {
        color: #0f3460;
        font-size: 1.15rem;
    }

    .nav-link {
        color: #5f6873;
        font-weight: 500;
        padding: 10px 14px !important;
        transition: 0.2s;
    }

    .nav-link:hover {
        color: #0f3460;
    }

    .usuario-btn {
        border: none;
        background: transparent;
    }

    .usuario-btn:hover {
        background-color: #f1f5f9;
    }

    .usuario-icono {
        width: 40px;
        height: 40px;
        border-radius: 50%;
        background-color: #0f3460;
        color: white;

        display: flex;
        align-items: center;
        justify-content: center;

        font-size: 1.1rem;
    }

    .dropdown-menu {
        border: none;
        border-radius: 12px;
    }

    .dropdown-item {
        padding: 10px 15px;
    }
</style>