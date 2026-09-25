<footer class="main-footer">
    <div class="container">
        <div class="footer-content">

            <div class="footer-brand">
                <img src="/favicon.ico" alt="CUL" />

                <div>
                    <h5>Gestión de Semilleros</h5>
                    <p>Portal de investigación CUL</p>
                </div>
            </div>

            <div class="footer-info">
                <span>
                    <i class="bi bi-mortarboard-fill"></i>
                    Corporación Universitaria Latinoamericana
                </span>

                <span>
                    <i class="bi bi-code-slash"></i>
                    Proyecto académico
                </span>
            </div>

        </div>

        <hr />

        <div class="footer-bottom">
            <span>© 2026 CUL - Gestión de Semilleros</span>
            <span>Todos los derechos reservados</span>
        </div>
    </div>
</footer>

<style>
    .main-footer {
        background: #0f3460;
        color: white;
        margin-top: 60px;
        padding: 35px 0 20px;
    }

    .footer-content {
        display: flex;
        justify-content: space-between;
        align-items: center;
        gap: 30px;
    }

    .footer-brand {
        display: flex;
        align-items: center;
        gap: 12px;
    }

    .footer-brand img {
        width: 50px;
        height: 50px;
        object-fit: contain;
        background: white;
        border-radius: 10px;
        padding: 5px;
    }

    .footer-brand h5 {
        margin: 0;
        font-weight: 600;
    }

    .footer-brand p {
        margin: 3px 0 0;
        opacity: 0.75;
        font-size: 0.85rem;
    }

    .footer-info {
        display: flex;
        flex-direction: column;
        gap: 8px;
        text-align: right;
        font-size: 0.85rem;
        opacity: 0.85;
    }

    .footer-info i {
        margin-right: 6px;
    }

    .main-footer hr {
        border-color: rgba(255, 255, 255, 0.25);
        margin: 25px 0 15px;
    }

    .footer-bottom {
        display: flex;
        justify-content: space-between;
        font-size: 0.8rem;
        opacity: 0.7;
    }

    @media (max-width: 768px) {
        .footer-content {
            flex-direction: column;
            align-items: flex-start;
        }

        .footer-info {
            text-align: left;
        }

        .footer-bottom {
            flex-direction: column;
            gap: 5px;
        }
    }
</style>