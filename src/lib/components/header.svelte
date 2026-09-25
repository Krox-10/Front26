<script>
    import logo from '$lib/assets/cul.png';
</script>

<header class="main-header">
    <div class="container">
        <div class="header-content">

            <div class="header-brand">
                <img src={logo} alt="Logo CUL" />

                <div>
                    <h1>Gestión de Semilleros</h1>
                    <p>Portal de investigación CUL</p>
                </div>
            </div>

            <div class="header-icon">
                <i class="bi bi-mortarboard-fill"></i>
            </div>

        </div>
    </div>
</header>

<style>
    .main-header {
        background: linear-gradient(135deg, #0f3460, #164b7a);
        color: white;
        padding: 25px 0;
        box-shadow: 0 3px 10px rgba(0, 0, 0, 0.12);
    }

    .header-content {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .header-brand {
        display: flex;
        align-items: center;
        gap: 15px;
    }

    .header-brand img {
        width: 65px;
        height: 65px;
        object-fit: contain;
        background: white;
        border-radius: 12px;
        padding: 6px;
    }

    .header-brand h1 {
        font-size: 1.6rem;
        font-weight: 700;
        margin: 0;
    }

    .header-brand p {
        margin: 4px 0 0;
        opacity: 0.85;
        font-size: 0.95rem;
    }

    .header-icon {
        font-size: 2.5rem;
        opacity: 0.85;
    }

    @media (max-width: 576px) {
        .header-brand h1 {
            font-size: 1.25rem;
        }

        .header-brand p {
            font-size: 0.8rem;
        }

        .header-brand img {
            width: 52px;
            height: 52px;
        }

        .header-icon {
            display: none;
        }
    }
</style>