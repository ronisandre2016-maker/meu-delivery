[index.html.html](https://github.com/user-attachments/files/24942222/index.html.html)
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistema de Pedidos Online Profissional</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --cor-primaria: #f97316;
            --cor-secundaria: #ef4444;
            --cor-texto: #1f2937;
            --cor-fundo: #f9fafb;
            --cor-sucesso: #10b981;
            --cor-info: #3b82f6;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            background-color: var(--cor-fundo);
            -webkit-tap-highlight-color: transparent;
        }

        .hidden {
            display: none !important;
        }

        /* Header */
        .header {
            background: linear-gradient(135deg, var(--cor-primaria), var(--cor-secundaria));
            color: white;
            padding: 1.25rem;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
        }

        .header-content {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1rem;
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
        }

        .logo-container {
            width: 56px;
            height: 56px;
            border-radius: 12px;
            background: white;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        }

        .logo-container img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .logo-placeholder {
            font-size: 1.75rem;
        }

        .header-info {
            flex: 1;
        }

        .header h1 {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 0.25rem;
        }

        .header-subtitle {
            font-size: 0.875rem;
            opacity: 0.9;
        }

        .admin-btn {
            background: rgba(255, 255, 255, 0.25);
            color: white;
            border: 2px solid white;
            padding: 0.5rem 1.25rem;
            border-radius: 8px;
            cursor: pointer;
            font-size: 0.875rem;
            font-weight: 600;
            transition: all 0.2s;
            backdrop-filter: blur(10px);
        }

        .admin-btn:hover {
            background: white;
            color: var(--cor-primaria);
        }

        .search-box {
            position: relative;
            margin-bottom: 1rem;
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
        }

        .search-box input {
            width: 100%;
            padding: 0.75rem 1rem 0.75rem 3rem;
            border-radius: 12px;
            border: none;
            font-size: 1rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        }

        .search-icon {
            position: absolute;
            left: 1rem;
            top: 50%;
            transform: translateY(-50%);
            color: #9ca3af;
            font-size: 1.25rem;
        }

        .categories {
            display: flex;
            gap: 0.75rem;
            overflow-x: auto;
            padding-bottom: 0.5rem;
            -webkit-overflow-scrolling: touch;
            scrollbar-width: none;
            max-width: 1200px;
            margin-left: auto;
            margin-right: auto;
        }

        .categories::-webkit-scrollbar {
            display: none;
        }

        .category-btn {
            padding: 0.5rem 1.5rem;
            border-radius: 20px;
            border: 2px solid white;
            white-space: nowrap;
            font-size: 0.875rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
            backdrop-filter: blur(10px);
        }

        .category-btn.active {
            background: white;
            color: var(--cor-primaria);
        }

        .category-btn:not(.active) {
            background: rgba(255, 255, 255, 0.25);
            color: white;
        }

        /* Produtos */
        .products-container {
            padding: 1.5rem;
            padding-bottom: 6rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        .product-card {
            background: white;
            border-radius: 16px;
            box-shadow: 0 2px 12px rgba(0, 0, 0, 0.08);
            overflow: hidden;
            transition: all 0.3s;
            cursor: pointer;
        }

        .product-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 24px rgba(0, 0, 0, 0.15);
        }

        .product-image {
            width: 100%;
            height: 200px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #fed7aa 0%, #fecaca 100%);
            font-size: 4rem;
            overflow: hidden;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .product-info {
            padding: 1.25rem;
        }

        .product-name {
            font-weight: 700;
            font-size: 1.125rem;
            color: var(--cor-texto);
            margin-bottom: 0.5rem;
        }

        .product-description {
            font-size: 0.875rem;
            color: #6b7280;
            margin-bottom: 1rem;
            line-height: 1.5;
        }

        .product-footer {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 1rem;
        }

        .product-price {
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--cor-primaria);
        }

        .btn-add {
            background: var(--cor-primaria);
            color: white;
            padding: 0.75rem 1.5rem;
            border-radius: 10px;
            border: none;
            font-weight: 600;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transition: all 0.2s;
        }

        .btn-add:hover {
            background: var(--cor-secundaria);
            transform: scale(1.05);
        }

        .btn-add:active {
            transform: scale(0.95);
        }

        /* Botão flutuante do carrinho */
        .cart-float {
            position: fixed;
            bottom: 1.5rem;
            right: 1.5rem;
            background: var(--cor-primaria);
            color: white;
            width: 64px;
            height: 64px;
            border-radius: 50%;
            border: none;
            box-shadow: 0 12px 28px rgba(249, 115, 22, 0.4);
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 50;
            transition: all 0.3s;
        }

        .cart-float:hover {
            transform: scale(1.1);
            box-shadow: 0 16px 32px rgba(249, 115, 22, 0.5);
        }

        .cart-badge {
            position: absolute;
            top: -8px;
            right: -8px;
            background: var(--cor-secundaria);
            color: white;
            font-size: 0.75rem;
            font-weight: 700;
            width: 28px;
            height: 28px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            border: 3px solid white;
        }

        /* Modal */
        .modal {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.6);
            backdrop-filter: blur(4px);
            z-index: 9999;
            display: flex;
            align-items: flex-end;
            justify-content: center;
            animation: fadeIn 0.2s ease-out;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        @media (min-width: 768px) {
            .modal {
                align-items: center;
            }
        }

        .modal-content {
            background: white;
            width: 100%;
            max-width: 500px;
            border-radius: 24px 24px 0 0;
            max-height: 90vh;
            overflow-y: auto;
            animation: slideUp 0.3s ease-out;
        }

        @media (min-width: 768px) {
            .modal-content {
                border-radius: 24px;
            }
        }

        @keyframes slideUp {
            from {
                transform: translateY(100%);
            }
            to {
                transform: translateY(0);
            }
        }

        .modal-header {
            background: linear-gradient(135deg, var(--cor-primaria), var(--cor-secundaria));
            color: white;
            padding: 1.5rem;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-radius: 24px 24px 0 0;
        }

        .modal-header h2 {
            font-size: 1.5rem;
            font-weight: 700;
        }

        .btn-close {
            background: none;
            border: none;
            color: white;
            font-size: 2rem;
            cursor: pointer;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            transition: background 0.2s;
        }

        .btn-close:hover {
            background: rgba(255, 255, 255, 0.2);
        }

        .modal-body {
            padding: 1.5rem;
        }

        .cart-item {
            display: flex;
            gap: 1rem;
            padding: 1rem;
            background: var(--cor-fundo);
            border-radius: 12px;
            margin-bottom: 1rem;
        }

        .cart-item-image {
            width: 80px;
            height: 80px;
            background: linear-gradient(135deg, #fed7aa, #fecaca);
            border-radius: 10px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            flex-shrink: 0;
            overflow: hidden;
        }

        .cart-item-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .cart-item-info {
            flex: 1;
        }

        .cart-item-name {
            font-weight: 700;
            margin-bottom: 0.25rem;
        }

        .cart-item-price {
            color: var(--cor-primaria);
            font-weight: 700;
        }

        .quantity-controls {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            margin-top: 0.5rem;
        }

        .btn-qty {
            background: var(--cor-primaria);
            color: white;
            border: none;
            width: 32px;
            height: 32px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: 700;
            font-size: 1.125rem;
            transition: all 0.2s;
        }

        .btn-qty:hover {
            background: var(--cor-secundaria);
        }

        .qty-display {
            font-weight: 700;
            min-width: 32px;
            text-align: center;
        }

        .cart-total {
            background: var(--cor-fundo);
            padding: 1.5rem;
            border-radius: 12px;
            margin-top: 1.5rem;
        }

        .total-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.75rem;
            font-size: 1.125rem;
        }

        .total-row.final {
            font-size: 1.5rem;
            font-weight: 800;
            color: var(--cor-primaria);
            padding-top: 0.75rem;
            border-top: 2px solid #e5e7eb;
        }

        .btn-whatsapp {
            background: #25d366;
            color: white;
            padding: 1rem;
            border-radius: 12px;
            border: none;
            width: 100%;
            font-weight: 700;
            font-size: 1.125rem;
            cursor: pointer;
            margin-top: 1rem;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 0.75rem;
            transition: all 0.2s;
        }

        .btn-whatsapp:hover {
            background: #20ba5a;
            transform: scale(1.02);
        }

        .empty-cart {
            text-align: center;
            padding: 3rem 1rem;
            color: #9ca3af;
        }

        .empty-cart-icon {
            font-size: 4rem;
            margin-bottom: 1rem;
        }

        /* Painel Admin */
        .admin-panel {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.7);
            backdrop-filter: blur(8px);
            z-index: 300;
            overflow-y: auto;
        }

        .admin-container {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 1rem;
        }

        .admin-content {
            background: white;
            border-radius: 24px;
            width: 100%;
            max-width: 1000px;
            margin: 2rem auto;
        }

        .admin-header {
            background: linear-gradient(135deg, var(--cor-primaria), var(--cor-secundaria));
            color: white;
            padding: 2rem;
            border-radius: 24px 24px 0 0;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .admin-header h2 {
            font-size: 2rem;
            font-weight: 800;
        }

        .admin-body {
            padding: 2rem;
        }

        /* Login Admin */
        .login-box {
            max-width: 400px;
            margin: 0 auto;
            text-align: center;
        }

        .login-icon {
            font-size: 4rem;
            margin-bottom: 1.5rem;
        }

        .login-title {
            font-size: 1.75rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            color: var(--cor-texto);
        }

        .login-subtitle {
            color: #6b7280;
            margin-bottom: 2rem;
        }

        .form-group {
            margin-bottom: 1.5rem;
            text-align: left;
        }

        .form-label {
            display: block;
            font-weight: 600;
            margin-bottom: 0.5rem;
            color: var(--cor-texto);
        }

        .form-input {
            width: 100%;
            padding: 0.875rem 1rem;
            border: 2px solid #e5e7eb;
            border-radius: 10px;
            font-size: 1rem;
            transition: all 0.2s;
        }

        .form-input:focus {
            outline: none;
            border-color: var(--cor-primaria);
            box-shadow: 0 0 0 3px rgba(249, 115, 22, 0.1);
        }

        .btn-primary {
            background: var(--cor-primaria);
            color: white;
            padding: 1rem 2rem;
            border-radius: 10px;
            border: none;
            font-weight: 700;
            font-size: 1rem;
            cursor: pointer;
            width: 100%;
            transition: all 0.2s;
        }

        .btn-primary:hover {
            background: var(--cor-secundaria);
            transform: translateY(-2px);
            box-shadow: 0 8px 16px rgba(249, 115, 22, 0.3);
        }

        .btn-secondary {
            background: #6b7280;
            color: white;
            padding: 0.75rem 1.5rem;
            border-radius: 10px;
            border: none;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
        }

        .btn-secondary:hover {
            background: #4b5563;
        }

        /* Dashboard Admin */
        .admin-tabs {
            display: flex;
            gap: 1rem;
            margin-bottom: 2rem;
            border-bottom: 2px solid #e5e7eb;
            overflow-x: auto;
        }

        .admin-tab {
            padding: 1rem 1.5rem;
            border: none;
            background: none;
            cursor: pointer;
            font-weight: 600;
            color: #6b7280;
            position: relative;
            white-space: nowrap;
            transition: all 0.2s;
        }

        .admin-tab.active {
            color: var(--cor-primaria);
        }

        .admin-tab.active::after {
            content: '';
            position: absolute;
            bottom: -2px;
            left: 0;
            right: 0;
            height: 3px;
            background: var(--cor-primaria);
            border-radius: 3px 3px 0 0;
        }

        .tab-content {
            display: none;
        }

        .tab-content.active {
            display: block;
        }

        /* Dashboard Stats */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .stat-card {
            background: linear-gradient(135deg, var(--cor-primaria), var(--cor-secundaria));
            color: white;
            padding: 1.5rem;
            border-radius: 16px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        .stat-icon {
            font-size: 2rem;
            margin-bottom: 0.75rem;
        }

        .stat-label {
            font-size: 0.875rem;
            opacity: 0.9;
            margin-bottom: 0.5rem;
        }

        .stat-value {
            font-size: 2rem;
            font-weight: 800;
        }

        /* Produtos Admin */
        .product-admin-card {
            background: white;
            border: 2px solid #e5e7eb;
            border-radius: 12px;
            padding: 1.5rem;
            margin-bottom: 1rem;
            display: flex;
            gap: 1.5rem;
            align-items: center;
            transition: all 0.2s;
        }

        .product-admin-card:hover {
            border-color: var(--cor-primaria);
            box-shadow: 0 4px 12px rgba(249, 115, 22, 0.15);
        }

        .product-admin-image {
            width: 100px;
            height: 100px;
            background: linear-gradient(135deg, #fed7aa, #fecaca);
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2.5rem;
            flex-shrink: 0;
            overflow: hidden;
        }

        .product-admin-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .product-admin-info {
            flex: 1;
        }

        .product-admin-name {
            font-weight: 700;
            font-size: 1.125rem;
            margin-bottom: 0.25rem;
        }

        .product-admin-meta {
            color: #6b7280;
            font-size: 0.875rem;
            margin-bottom: 0.5rem;
        }

        .product-admin-price {
            color: var(--cor-primaria);
            font-weight: 700;
            font-size: 1.25rem;
        }

        .product-admin-actions {
            display: flex;
            gap: 0.75rem;
        }

        .btn-edit {
            background: var(--cor-info);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 8px;
            border: none;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
        }

        .btn-edit:hover {
            background: #2563eb;
        }

        .btn-delete {
            background: var(--cor-secundaria);
            color: white;
            padding: 0.5rem 1rem;
            border-radius: 8px;
            border: none;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
        }

        .btn-delete:hover {
            background: #dc2626;
        }

        /* Upload de Imagem */
        .image-upload {
            border: 2px dashed #d1d5db;
            border-radius: 12px;
            padding: 2rem;
            text-align: center;
            cursor: pointer;
            transition: all 0.2s;
            background: var(--cor-fundo);
        }

        .image-upload:hover {
            border-color: var(--cor-primaria);
            background: #fef3f2;
        }

        .image-upload.has-image {
            padding: 0;
            border: none;
        }

        .image-preview {
            width: 100%;
            max-height: 300px;
            border-radius: 12px;
            overflow: hidden;
        }

        .image-preview img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .upload-icon {
            font-size: 3rem;
            color: #9ca3af;
            margin-bottom: 1rem;
        }

        .upload-text {
            color: #6b7280;
            font-weight: 600;
        }

        .upload-hint {
            color: #9ca3af;
            font-size: 0.875rem;
            margin-top: 0.5rem;
        }

        /* Configurações */
        .config-section {
            background: var(--cor-fundo);
            padding: 1.5rem;
            border-radius: 12px;
            margin-bottom: 1.5rem;
        }

        .config-section h3 {
            font-size: 1.25rem;
            font-weight: 700;
            margin-bottom: 1.5rem;
            color: var(--cor-texto);
        }

        .color-picker-group {
            display: flex;
            gap: 1rem;
            align-items: center;
        }

        .color-input-wrapper {
            flex: 1;
        }

        .color-preview {
            width: 60px;
            height: 60px;
            border-radius: 10px;
            border: 3px solid #e5e7eb;
            cursor: pointer;
            transition: all 0.2s;
        }

        .color-preview:hover {
            transform: scale(1.1);
        }

        /* Responsivo */
        @media (max-width: 768px) {
            .products-grid {
                grid-template-columns: 1fr;
            }

            .stats-grid {
                grid-template-columns: 1fr;
            }

            .product-admin-card {
                flex-direction: column;
                text-align: center;
            }

            .product-admin-actions {
                width: 100%;
                flex-direction: column;
            }

            .btn-edit, .btn-delete {
                width: 100%;
            }
        }

        /* Botão adicionar produto */
        .btn-add-product {
            background: var(--cor-sucesso);
            color: white;
            padding: 1rem 2rem;
            border-radius: 12px;
            border: none;
            font-weight: 700;
            font-size: 1rem;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 0.75rem;
            transition: all 0.2s;
            margin-bottom: 1.5rem;
        }

        .btn-add-product:hover {
            background: #059669;
            transform: translateY(-2px);
            box-shadow: 0 8px 16px rgba(16, 185, 129, 0.3);
        }

        /* Modal Checkout */
        .checkout-form {
            display: flex;
            flex-direction: column;
            gap: 1rem;
        }

        .checkout-summary {
            background: var(--cor-fundo);
            padding: 1rem;
            border-radius: 12px;
            margin-bottom: 1rem;
        }

        .checkout-item {
            display: flex;
            justify-content: space-between;
            padding: 0.5rem 0;
            border-bottom: 1px solid #e5e7eb;
        }

        .checkout-item:last-child {
            border-bottom: none;
        }

        .checkout-total {
            background: linear-gradient(135deg, var(--cor-primaria), var(--cor-secundaria));
            color: white;
            padding: 1rem;
            border-radius: 12px;
            margin-top: 1rem;
            text-align: center;
            font-size: 1.25rem;
            font-weight: 700;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <div class="header">
        <div class="header-content">
            <div class="logo-container" id="logo-display">
                <span class="logo-placeholder">🍕</span>
            </div>
            <div class="header-info">
                <h1 id="nome-empresa">Meu Negócio</h1>
                <div class="header-subtitle">Peça online e receba em casa</div>
            </div>
            <button class="admin-btn" onclick="mostrarLoginAdmin()">
                🔐 Admin
            </button>
        </div>

        <div class="search-box">
            <span class="search-icon">🔍</span>
            <input type="text" id="search-input" placeholder="Buscar produtos..." oninput="buscarProdutos()">
        </div>

        <div class="categories" id="categories"></div>
    </div>

    <!-- Produtos -->
    <div class="products-container">
        <div class="products-grid" id="products-list"></div>
    </div>

    <!-- Botão Carrinho Flutuante -->
    <button class="cart-float" onclick="abrirCarrinho()">
        🛒
        <span class="cart-badge hidden" id="cart-badge">0</span>
    </button>

    <!-- Modal Carrinho -->
    <div id="cart-modal" class="modal hidden">
        <div class="modal-content">
            <div class="modal-header">
                <h2>🛒 Meu Carrinho</h2>
                <button class="btn-close" onclick="fecharCarrinho()">×</button>
            </div>
            <div class="modal-body">
                <div id="cart-items"></div>
                <div id="cart-total" class="cart-total hidden">
                    <div class="total-row">
                        <span>Subtotal:</span>
                        <span id="subtotal">R$ 0,00</span>
                    </div>
                    <div class="total-row">
                        <span>Taxa de entrega:</span>
                        <span id="taxa-entrega">R$ 0,00</span>
                    </div>
                    <div class="total-row final">
                        <span>Total:</span>
                        <span id="total-final">R$ 0,00</span>
                    </div>
                    <button class="btn-whatsapp" onclick="abrirCheckout()">
                        💬 Continuar para Checkout
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Modal Checkout -->
    <div id="checkout-modal" class="modal hidden">
        <div class="modal-content">
            <div class="modal-header">
                <h2>📋 Finalizar Pedido</h2>
                <button class="btn-close" onclick="fecharCheckout()">×</button>
            </div>
            <div class="modal-body">
                <!-- Resumo do Pedido -->
                <div class="checkout-summary">
                    <h3 style="margin-bottom: 1rem; color: var(--cor-texto);">📦 Resumo do Pedido</h3>
                    <div id="checkout-items"></div>
                </div>

                <!-- Formulário de Dados -->
                <form class="checkout-form" onsubmit="enviarPedidoWhatsApp(event)">
                    <div class="form-group">
                        <label class="form-label">Nome Completo *</label>
                        <input type="text" id="cliente-nome" class="form-input" placeholder="Digite seu nome completo" required>
                    </div>

                    <div class="form-group">
                        <label class="form-label">WhatsApp (com DDD) *</label>
                        <input type="tel" id="cliente-whatsapp" class="form-input" placeholder="(85) 99999-9999" required maxlength="15" oninput="formatarTelefone(this)">
                    </div>

                    <div class="form-group">
                        <label class="form-label">Endereço Completo *</label>
                        <input type="text" id="cliente-endereco" class="form-input" placeholder="Rua, número, bairro" required>
                    </div>

                    <div class="form-group">
                        <label class="form-label">Complemento</label>
                        <input type="text" id="cliente-complemento" class="form-input" placeholder="Apartamento, bloco, etc (opcional)">
                    </div>

                    <div class="form-group">
                        <label class="form-label">Observações</label>
                        <textarea id="cliente-observacoes" class="form-input" rows="3" placeholder="Alguma observação sobre o pedido? (opcional)"></textarea>
                    </div>

                    <div class="checkout-total" id="checkout-total">
                        Total: R$ 0,00
                    </div>

                    <button type="submit" class="btn-whatsapp" style="margin-top: 1rem;">
                        💬 Enviar Pedido pelo WhatsApp
                    </button>
                </form>
            </div>
        </div>
    </div>

    <!-- Painel Admin -->
    <div id="admin-panel" class="admin-panel hidden">
        <div class="admin-container">
            <div class="admin-content">
                <!-- Login Admin -->
                <div id="admin-login">
                    <div class="admin-header">
                        <h2>🔐 Área Administrativa</h2>
                        <button class="btn-close" onclick="fecharAdmin()">×</button>
                    </div>
                    <div class="admin-body">
                        <div class="login-box">
                            <div class="login-icon">🔒</div>
                            <h3 class="login-title">Acesso Restrito</h3>
                            <p class="login-subtitle">Insira sua senha de administrador</p>
                            <div class="form-group">
                                <label class="form-label">Senha</label>
                                <input type="password" id="senha-admin" class="form-input" placeholder="Digite sua senha">
                            </div>
                            <button class="btn-primary" onclick="fazerLoginAdmin()">Entrar</button>
                        </div>
                    </div>
                </div>

                <!-- Dashboard Admin -->
                <div id="admin-dashboard" class="hidden">
                    <div class="admin-header">
                        <h2>📊 Painel Administrativo</h2>
                        <button class="btn-close" onclick="fecharAdmin()">×</button>
                    </div>
                    <div class="admin-body">
                        <div class="admin-tabs">
                            <button class="admin-tab active" data-tab="dashboard" onclick="mudarTab('dashboard')">📊 Dashboard</button>
                            <button class="admin-tab" data-tab="produtos" onclick="mudarTab('produtos')">🍽️ Produtos</button>
                            <button class="admin-tab" data-tab="pedidos" onclick="mudarTab('pedidos')">📦 Pedidos</button>
                            <button class="admin-tab" data-tab="config" onclick="mudarTab('config')">⚙️ Configurações</button>
                        </div>

                        <!-- Tab Dashboard -->
                        <div id="tab-dashboard" class="tab-content active">
                            <div class="stats-grid">
                                <div class="stat-card">
                                    <div class="stat-icon">📦</div>
                                    <div class="stat-label">Total de Produtos</div>
                                    <div class="stat-value" id="stat-produtos">0</div>
                                </div>
                                <div class="stat-card">
                                    <div class="stat-icon">🏷️</div>
                                    <div class="stat-label">Categorias</div>
                                    <div class="stat-value" id="stat-categorias">0</div>
                                </div>
                                <div class="stat-card">
                                    <div class="stat-icon">👥</div>
                                    <div class="stat-label">Pedidos Hoje</div>
                                    <div class="stat-value" id="stat-pedidos">0</div>
                                </div>
                                <div class="stat-card">
                                    <div class="stat-icon">💰</div>
                                    <div class="stat-label">Faturamento Hoje</div>
                                    <div class="stat-value" id="stat-faturamento">R$ 0</div>
                                </div>
                            </div>
                            <div class="config-section">
                                <h3>📈 Atividade Recente</h3>
                                <p style="color: #6b7280;">Os pedidos serão exibidos aqui conforme forem sendo realizados.</p>
                            </div>
                        </div>

                        <!-- Tab Produtos -->
                        <div id="tab-produtos" class="tab-content">
                            <button class="btn-add-product" onclick="abrirFormProduto(null)">
                                ➕ Adicionar Novo Produto
                            </button>
                            <div id="lista-produtos-admin"></div>
                        </div>

                        <!-- Tab Pedidos -->
                        <div id="tab-pedidos" class="tab-content">
                            <div class="config-section">
                                <h3>📦 Histórico de Pedidos</h3>
                                <p style="color: #6b7280;">Os pedidos realizados aparecerão aqui. Por enquanto, não há pedidos registrados.</p>
                            </div>
                        </div>

                        <!-- Tab Configurações -->
                        <div id="tab-config" class="tab-content">
                            <div class="config-section">
                                <h3>🏢 Informações do Negócio</h3>
                                <div class="form-group">
                                    <label class="form-label">Nome do Negócio</label>
                                    <input type="text" id="admin-nome-empresa" class="form-input" placeholder="Ex: Pizzaria Sabor Italiano">
                                </div>
                                <div class="form-group">
                                    <label class="form-label">Logo (Upload de Imagem)</label>
                                    <div class="image-upload" id="logo-upload-area" onclick="document.getElementById('admin-logo').click()">
                                        <div id="logo-preview">
                                            <div class="upload-icon">🖼️</div>
                                            <div class="upload-text">Clique para fazer upload da logo</div>
                                            <div class="upload-hint">PNG, JPG ou GIF (max. 2MB)</div>
                                        </div>
                                    </div>
                                    <input type="file" id="admin-logo" accept="image/*" style="display: none;" onchange="carregarLogo(this)">
                                </div>
                                <div class="form-group">
                                    <label class="form-label">WhatsApp (apenas números)</label>
                                    <input type="text" id="admin-whatsapp" class="form-input" placeholder="85999999999">
                                </div>
                            </div>

                            <div class="config-section">
                                <h3>🎨 Personalização Visual</h3>
                                <div class="form-group">
                                    <label class="form-label">Cor Primária</label>
                                    <div class="color-picker-group">
                                        <div class="color-input-wrapper">
                                            <input type="text" id="admin-cor-primaria-hex" class="form-input" value="#f97316">
                                        </div>
                                        <div class="color-preview" id="cor-primaria-preview" style="background: #f97316;" onclick="document.getElementById('admin-cor-primaria').click()"></div>
                                        <input type="color" id="admin-cor-primaria" value="#f97316" style="display: none;">
                                    </div>
                                </div>
                                <div class="form-group">
                                    <label class="form-label">Cor Secundária</label>
                                    <div class="color-picker-group">
                                        <div class="color-input-wrapper">
                                            <input type="text" id="admin-cor-secundaria-hex" class="form-input" value="#ef4444">
                                        </div>
                                        <div class="color-preview" id="cor-secundaria-preview" style="background: #ef4444;" onclick="document.getElementById('admin-cor-secundaria').click()"></div>
                                        <input type="color" id="admin-cor-secundaria" value="#ef4444" style="display: none;">
                                    </div>
                                </div>
                            </div>

                            <div class="config-section">
                                <h3>🔒 Segurança</h3>
                                <div class="form-group">
                                    <label class="form-label">Alterar Senha de Administrador</label>
                                    <input type="password" id="admin-nova-senha" class="form-input" placeholder="Nova senha (mínimo 4 caracteres)">
                                </div>
                                <button class="btn-secondary" onclick="alterarSenhaAdmin()">Alterar Senha</button>
                            </div>

                            <button class="btn-primary" onclick="salvarConfiguracoes()">💾 Salvar Todas as Configurações</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Modal Formulário Produto -->
    <div id="form-produto-modal" class="modal hidden">
        <div class="modal-content">
            <div class="modal-header">
                <h2 id="form-produto-titulo">➕ Adicionar Produto</h2>
                <button class="btn-close" onclick="fecharFormProduto()">×</button>
            </div>
            <div class="modal-body">
                <div class="form-group">
                    <label class="form-label">Nome do Produto *</label>
                    <input type="text" id="produto-nome" class="form-input" placeholder="Ex: Pizza Margherita">
                </div>
                <div class="form-group">
                    <label class="form-label">Descrição *</label>
                    <input type="text" id="produto-descricao" class="form-input" placeholder="Ex: Molho, mussarela e manjericão">
                </div>
                <div class="form-group">
                    <label class="form-label">Preço (R$) *</label>
                    <input type="number" id="produto-preco" class="form-input" placeholder="0.00" step="0.01" min="0">
                </div>
                <div class="form-group">
                    <label class="form-label">Categoria *</label>
                    <input type="text" id="produto-categoria" class="form-input" placeholder="Ex: Pizzas">
                </div>
                <div class="form-group">
                    <label class="form-label">Imagem do Produto</label>
                    <div class="image-upload" id="produto-image-upload-area" onclick="document.getElementById('produto-imagem-file').click()">
                        <div id="produto-image-preview">
                            <div class="upload-icon">📸</div>
                            <div class="upload-text">Clique para fazer upload da imagem</div>
                            <div class="upload-hint">PNG, JPG ou GIF (max. 2MB)</div>
                        </div>
                    </div>
                    <input type="file" id="produto-imagem-file" accept="image/*" style="display: none;" onchange="carregarImagemProduto(this)">
                    <input type="hidden" id="produto-imagem-data">
                    <input type="hidden" id="produto-id-edit">
                </div>
                <div style="display: flex; gap: 1rem; margin-top: 1.5rem;">
                    <button class="btn-secondary" onclick="fecharFormProduto()" style="flex: 1;">Cancelar</button>
                    <button class="btn-primary" onclick="salvarProduto()" style="flex: 1;">💾 Salvar Produto</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Dados
        let CONFIG = {
            nomeEmpresa: 'Meu Negócio',
            corPrimaria: '#f97316',
            corSecundaria: '#ef4444',
            whatsapp: '85999999999',
            senhaAdmin: 'admin123',
            logo: '',
            taxaEntrega: 5.00
        };

        let PRODUTOS = [
            {
                id: 1,
                nome: 'Pizza Margherita',
                descricao: 'Molho de tomate, mussarela e manjericão fresco',
                preco: 35.90,
                categoria: 'Pizzas',
                imagem: ''
            },
            {
                id: 2,
                nome: 'Hambúrguer Especial',
                descricao: 'Hambúrguer 180g, queijo, bacon, alface e tomate',
                preco: 28.50,
                categoria: 'Lanches',
                imagem: ''
            },
            {
                id: 3,
                nome: 'Refrigerante Lata',
                descricao: 'Coca-Cola, Guaraná ou Sprite 350ml',
                preco: 5.00,
                categoria: 'Bebidas',
                imagem: ''
            }
        ];

        let carrinho = [];
        let categoriaAtiva = 'Todos';

        // Estatísticas simuladas
        let estatisticas = {
            pedidosHoje: 12,
            faturamentoHoje: 567.80
        };

        // Inicialização
        window.onload = function() {
            carregarConfiguracoes();
            carregarProdutos();
            carregarCarrinho();
            aplicarTema();
            renderizarCategorias();
            renderizarProdutos();
            atualizarCarrinhoBadge();
            
            // Event listener para Enter no login
            document.getElementById('senha-admin').addEventListener('keypress', function(e) {
                if (e.key === 'Enter') fazerLoginAdmin();
            });

            // Event listeners para cores
            setupColorPickers();
        };

        function setupColorPickers() {
            const corPrimariaInput = document.getElementById('admin-cor-primaria');
            const corPrimariaHex = document.getElementById('admin-cor-primaria-hex');
            const corPrimariaPreview = document.getElementById('cor-primaria-preview');

            corPrimariaInput.addEventListener('input', function(e) {
                const cor = e.target.value;
                corPrimariaHex.value = cor;
                corPrimariaPreview.style.background = cor;
                CONFIG.corPrimaria = cor;
                aplicarTema();
            });

            corPrimariaHex.addEventListener('input', function(e) {
                const cor = e.target.value;
                if (/^#[0-9A-F]{6}$/i.test(cor)) {
                    corPrimariaInput.value = cor;
                    corPrimariaPreview.style.background = cor;
                    CONFIG.corPrimaria = cor;
                    aplicarTema();
                }
            });

            const corSecundariaInput = document.getElementById('admin-cor-secundaria');
            const corSecundariaHex = document.getElementById('admin-cor-secundaria-hex');
            const corSecundariaPreview = document.getElementById('cor-secundaria-preview');

            corSecundariaInput.addEventListener('input', function(e) {
                const cor = e.target.value;
                corSecundariaHex.value = cor;
                corSecundariaPreview.style.background = cor;
                CONFIG.corSecundaria = cor;
                aplicarTema();
            });

            corSecundariaHex.addEventListener('input', function(e) {
                const cor = e.target.value;
                if (/^#[0-9A-F]{6}$/i.test(cor)) {
                    corSecundariaInput.value = cor;
                    corSecundariaPreview.style.background = cor;
                    CONFIG.corSecundaria = cor;
                    aplicarTema();
                }
            });
        }

        // Renderização
        function renderizarCategorias() {
            const categorias = ['Todos', ...new Set(PRODUTOS.map(p => p.categoria))];
            const container = document.getElementById('categories');
            
            container.innerHTML = categorias.map(cat => 
                '<button class="category-btn ' + (cat === categoriaAtiva ? 'active' : '') + '" onclick="filtrarCategoria(\'' + cat + '\')">' + cat + '</button>'
            ).join('');
        }

        function renderizarProdutos() {
            const produtosFiltrados = categoriaAtiva === 'Todos' 
                ? PRODUTOS 
                : PRODUTOS.filter(p => p.categoria === categoriaAtiva);

            const searchTerm = document.getElementById('search-input').value.toLowerCase();
            const produtosBuscados = searchTerm 
                ? produtosFiltrados.filter(p => 
                    p.nome.toLowerCase().includes(searchTerm) || 
                    p.descricao.toLowerCase().includes(searchTerm))
                : produtosFiltrados;

            const container = document.getElementById('products-list');
            
            if (produtosBuscados.length === 0) {
                container.innerHTML = '<div class="empty-cart"><div class="empty-cart-icon">🔍</div><h3>Nenhum produto encontrado</h3><p>Tente buscar por outro termo ou categoria</p></div>';
                return;
            }

            container.innerHTML = produtosBuscados.map(produto => {
                const imagemHtml = produto.imagem 
                    ? '<img src="' + produto.imagem + '" alt="' + produto.nome + '">' 
                    : '🍽️';
                
                return '<div class="product-card">' +
                    '<div class="product-image">' + imagemHtml + '</div>' +
                    '<div class="product-info">' +
                        '<div class="product-name">' + produto.nome + '</div>' +
                        '<div class="product-description">' + produto.descricao + '</div>' +
                        '<div class="product-footer">' +
                            '<div class="product-price">R$ ' + produto.preco.toFixed(2) + '</div>' +
                            '<button class="btn-add" onclick="adicionarAoCarrinho(' + produto.id + ')">➕ Adicionar</button>' +
                        '</div>' +
                    '</div>' +
                '</div>';
            }).join('');
        }

        function filtrarCategoria(categoria) {
            categoriaAtiva = categoria;
            renderizarCategorias();
            renderizarProdutos();
        }

        function buscarProdutos() {
            renderizarProdutos();
        }

        // Carrinho
        function adicionarAoCarrinho(produtoId) {
            const produto = PRODUTOS.find(p => p.id === produtoId);
            const itemExistente = carrinho.find(item => item.id === produtoId);

            if (itemExistente) {
                itemExistente.quantidade++;
            } else {
                carrinho.push({
                    id: produto.id,
                    nome: produto.nome,
                    descricao: produto.descricao,
                    preco: produto.preco,
                    imagem: produto.imagem,
                    quantidade: 1
                });
            }

            salvarCarrinho();
            atualizarCarrinhoBadge();
            
            // Feedback visual
            const badge = document.getElementById('cart-badge');
            badge.style.transform = 'scale(1.3)';
            setTimeout(function() { badge.style.transform = 'scale(1)'; }, 200);
        }

        function atualizarQuantidade(produtoId, delta) {
            const item = carrinho.find(i => i.id === produtoId);
            if (item) {
                item.quantidade += delta;
                if (item.quantidade <= 0) {
                    carrinho = carrinho.filter(i => i.id !== produtoId);
                }
                salvarCarrinho();
                renderizarCarrinho();
                atualizarCarrinhoBadge();
            }
        }

        function atualizarCarrinhoBadge() {
            const badge = document.getElementById('cart-badge');
            const total = carrinho.reduce(function(sum, item) { return sum + item.quantidade; }, 0);
            
            if (total > 0) {
                badge.textContent = total;
                badge.classList.remove('hidden');
            } else {
                badge.classList.add('hidden');
            }
        }

        function abrirCarrinho() {
            document.getElementById('cart-modal').classList.remove('hidden');
            renderizarCarrinho();
        }

        function fecharCarrinho() {
            document.getElementById('cart-modal').classList.add('hidden');
        }

        function renderizarCarrinho() {
            const container = document.getElementById('cart-items');
            const totalContainer = document.getElementById('cart-total');

            if (carrinho.length === 0) {
                container.innerHTML = '<div class="empty-cart"><div class="empty-cart-icon">🛒</div><h3>Carrinho vazio</h3><p>Adicione produtos para fazer seu pedido</p></div>';
                totalContainer.classList.add('hidden');
                return;
            }

            container.innerHTML = carrinho.map(function(item) {
                const imagemHtml = item.imagem 
                    ? '<img src="' + item.imagem + '" alt="' + item.nome + '">' 
                    : '🍽️';
                
                return '<div class="cart-item">' +
                    '<div class="cart-item-image">' + imagemHtml + '</div>' +
                    '<div class="cart-item-info">' +
                        '<div class="cart-item-name">' + item.nome + '</div>' +
                        '<div class="cart-item-price">R$ ' + item.preco.toFixed(2) + '</div>' +
                        '<div class="quantity-controls">' +
                            '<button class="btn-qty" onclick="atualizarQuantidade(' + item.id + ', -1)">−</button>' +
                            '<span class="qty-display">' + item.quantidade + '</span>' +
                            '<button class="btn-qty" onclick="atualizarQuantidade(' + item.id + ', 1)">+</button>' +
                        '</div>' +
                    '</div>' +
                '</div>';
            }).join('');

            const subtotal = carrinho.reduce(function(sum, item) { return sum + (item.preco * item.quantidade); }, 0);
            const taxaEntrega = CONFIG.taxaEntrega;
            const total = subtotal + taxaEntrega;

            document.getElementById('subtotal').textContent = 'R$ ' + subtotal.toFixed(2);
            document.getElementById('taxa-entrega').textContent = 'R$ ' + taxaEntrega.toFixed(2);
            document.getElementById('total-final').textContent = 'R$ ' + total.toFixed(2);
            totalContainer.classList.remove('hidden');
        }

        function abrirCheckout() {
            if (carrinho.length === 0) return;
            
            // Fechar o modal do carrinho
            fecharCarrinho();
            
            // Renderizar resumo do pedido
            renderizarResumoCheckout();
            
            // Abrir modal de checkout
            document.getElementById('checkout-modal').classList.remove('hidden');
            document.body.style.overflow = 'hidden';
            
            // Focar no primeiro campo
            setTimeout(function() {
                document.getElementById('cliente-nome').focus();
            }, 100);
        }

        function fecharCheckout() {
            document.getElementById('checkout-modal').classList.add('hidden');
            document.body.style.overflow = '';
            limparFormularioCheckout();
        }

        function renderizarResumoCheckout() {
            const container = document.getElementById('checkout-items');
            
            const html = carrinho.map(function(item) {
                const total = item.preco * item.quantidade;
                return '<div class="checkout-item">' +
                    '<span>' + item.quantidade + 'x ' + item.nome + '</span>' +
                    '<span style="font-weight: 600;">R$ ' + total.toFixed(2) + '</span>' +
                '</div>';
            }).join('');

            const subtotal = carrinho.reduce(function(sum, item) { 
                return sum + (item.preco * item.quantidade); 
            }, 0);
            const taxaEntrega = CONFIG.taxaEntrega;
            const total = subtotal + taxaEntrega;

            container.innerHTML = html + 
                '<div class="checkout-item" style="margin-top: 0.5rem; padding-top: 0.5rem; border-top: 2px solid #d1d5db;">' +
                    '<span>Subtotal</span>' +
                    '<span>R$ ' + subtotal.toFixed(2) + '</span>' +
                '</div>' +
                '<div class="checkout-item">' +
                    '<span>Taxa de Entrega</span>' +
                    '<span>R$ ' + taxaEntrega.toFixed(2) + '</span>' +
                '</div>';

            document.getElementById('checkout-total').textContent = 'Total: R$ ' + total.toFixed(2);
        }

        function limparFormularioCheckout() {
            document.getElementById('cliente-nome').value = '';
            document.getElementById('cliente-whatsapp').value = '';
            document.getElementById('cliente-endereco').value = '';
            document.getElementById('cliente-complemento').value = '';
            document.getElementById('cliente-observacoes').value = '';
        }

        function enviarPedidoWhatsApp(event) {
            event.preventDefault();
            
            const nome = document.getElementById('cliente-nome').value.trim();
            const whatsapp = document.getElementById('cliente-whatsapp').value.trim();
            const endereco = document.getElementById('cliente-endereco').value.trim();
            const complemento = document.getElementById('cliente-complemento').value.trim();
            const observacoes = document.getElementById('cliente-observacoes').value.trim();

            if (!nome || !whatsapp || !endereco) {
                alert('⚠️ Por favor, preencha todos os campos obrigatórios!');
                return;
            }

            // Montar mensagem do WhatsApp
            let mensagem = '*🛒 NOVO PEDIDO*\n\n';
            
            // Dados do cliente
            mensagem += '*👤 DADOS DO CLIENTE*\n';
            mensagem += '▫️ Nome: ' + nome + '\n';
            mensagem += '▫️ WhatsApp: ' + whatsapp + '\n';
            mensagem += '▫️ Endereço: ' + endereco + '\n';
            if (complemento) {
                mensagem += '▫️ Complemento: ' + complemento + '\n';
            }
            mensagem += '\n';

            // Itens do pedido
            mensagem += '*🍽️ ITENS DO PEDIDO*\n';
            carrinho.forEach(function(item) {
                mensagem += '▫️ ' + item.quantidade + 'x ' + item.nome + '\n';
                mensagem += '   R$ ' + item.preco.toFixed(2) + ' cada\n';
                mensagem += '   Subtotal: R$ ' + (item.preco * item.quantidade).toFixed(2) + '\n\n';
            });

            // Totais
            const subtotal = carrinho.reduce(function(sum, item) { 
                return sum + (item.preco * item.quantidade); 
            }, 0);
            const total = subtotal + CONFIG.taxaEntrega;

            mensagem += '*💰 VALORES*\n';
            mensagem += '▫️ Subtotal: R$ ' + subtotal.toFixed(2) + '\n';
            mensagem += '▫️ Taxa de Entrega: R$ ' + CONFIG.taxaEntrega.toFixed(2) + '\n';
            mensagem += '▫️ *TOTAL: R$ ' + total.toFixed(2) + '*\n';

            // Observações
            if (observacoes) {
                mensagem += '\n*📝 OBSERVAÇÕES*\n';
                mensagem += observacoes;
            }

            // Abrir WhatsApp
            const whatsappUrl = 'https://wa.me/' + CONFIG.whatsapp + '?text=' + encodeURIComponent(mensagem);
            window.open(whatsappUrl, '_blank');

            // Atualizar estatísticas
            estatisticas.pedidosHoje++;
            estatisticas.faturamentoHoje += total;
            localStorage.setItem('estatisticas', JSON.stringify(estatisticas));

            // Limpar carrinho e fechar modais
            carrinho = [];
            salvarCarrinho();
            atualizarBadgeCarrinho();
            fecharCheckout();
            
            // Mensagem de sucesso
            alert('✅ Pedido enviado! Você será redirecionado para o WhatsApp.');
        }

        function finalizarPedido() {
            // Função antiga mantida para compatibilidade
            abrirCheckout();
        }

        function formatarTelefone(input) {
            let valor = input.value.replace(/\D/g, '');
            
            if (valor.length <= 11) {
                if (valor.length <= 2) {
                    valor = valor.replace(/^(\d{0,2})/, '($1');
                } else if (valor.length <= 6) {
                    valor = valor.replace(/^(\d{2})(\d{0,4})/, '($1) $2');
                } else if (valor.length <= 10) {
                    valor = valor.replace(/^(\d{2})(\d{4})(\d{0,4})/, '($1) $2-$3');
                } else {
                    valor = valor.replace(/^(\d{2})(\d{5})(\d{0,4})/, '($1) $2-$3');
                }
            }
            
            input.value = valor;
        }

        // Admin
        function mostrarLoginAdmin() {
            document.getElementById('admin-panel').classList.remove('hidden');
            document.getElementById('admin-login').classList.remove('hidden');
            document.getElementById('admin-dashboard').classList.add('hidden');
            document.getElementById('senha-admin').value = '';
            setTimeout(function() { document.getElementById('senha-admin').focus(); }, 100);
        }

        function fazerLoginAdmin() {
            const senha = document.getElementById('senha-admin').value;
            if (senha === CONFIG.senhaAdmin) {
                document.getElementById('admin-login').classList.add('hidden');
                document.getElementById('admin-dashboard').classList.remove('hidden');
                carregarDadosAdmin();
                atualizarEstatisticas();
            } else {
                alert('❌ Senha incorreta!');
            }
        }

        function fecharAdmin() {
            document.getElementById('admin-panel').classList.add('hidden');
        }

        function mudarTab(tabName) {
            // Remover active de todas as tabs
            const tabs = document.querySelectorAll('.admin-tab');
            tabs.forEach(function(tab) {
                tab.classList.remove('active');
            });
            
            // Adicionar active na tab clicada
            const tabAtual = document.querySelector('.admin-tab[data-tab="' + tabName + '"]');
            if (tabAtual) {
                tabAtual.classList.add('active');
            }
            
            // Mostrar conteúdo correto
            const contents = document.querySelectorAll('.tab-content');
            contents.forEach(function(content) {
                content.classList.remove('active');
            });
            
            const contentAtual = document.getElementById('tab-' + tabName);
            if (contentAtual) {
                contentAtual.classList.add('active');
            }

            if (tabName === 'produtos') {
                renderizarListaProdutosAdmin();
            }
        }

        function atualizarEstatisticas() {
            const stats = JSON.parse(localStorage.getItem('estatisticas') || '{"pedidosHoje": 0, "faturamentoHoje": 0}');
            
            document.getElementById('stat-produtos').textContent = PRODUTOS.length;
            document.getElementById('stat-categorias').textContent = new Set(PRODUTOS.map(function(p) { return p.categoria; })).size;
            document.getElementById('stat-pedidos').textContent = stats.pedidosHoje;
            document.getElementById('stat-faturamento').textContent = 'R$ ' + stats.faturamentoHoje.toFixed(2);
        }

        function carregarDadosAdmin() {
            document.getElementById('admin-nome-empresa').value = CONFIG.nomeEmpresa;
            document.getElementById('admin-cor-primaria').value = CONFIG.corPrimaria;
            document.getElementById('admin-cor-primaria-hex').value = CONFIG.corPrimaria;
            document.getElementById('cor-primaria-preview').style.background = CONFIG.corPrimaria;
            document.getElementById('admin-cor-secundaria').value = CONFIG.corSecundaria;
            document.getElementById('admin-cor-secundaria-hex').value = CONFIG.corSecundaria;
            document.getElementById('cor-secundaria-preview').style.background = CONFIG.corSecundaria;
            document.getElementById('admin-whatsapp').value = CONFIG.whatsapp;

            if (CONFIG.logo) {
                document.getElementById('logo-preview').innerHTML = '<div class="image-preview"><img src="' + CONFIG.logo + '" alt="Logo"></div>';
                document.getElementById('logo-upload-area').classList.add('has-image');
            }

            // Event listeners
            document.getElementById('admin-nome-empresa').addEventListener('input', function(e) {
                CONFIG.nomeEmpresa = e.target.value;
                document.getElementById('nome-empresa').textContent = e.target.value;
            });

            document.getElementById('admin-whatsapp').addEventListener('input', function(e) {
                CONFIG.whatsapp = e.target.value.replace(/\D/g, '');
                e.target.value = CONFIG.whatsapp;
            });
        }

        function carregarLogo(input) {
            if (input.files && input.files[0]) {
                if (input.files[0].size > 2 * 1024 * 1024) {
                    alert('⚠️ A imagem deve ter no máximo 2MB');
                    return;
                }

                const reader = new FileReader();
                reader.onload = function(e) {
                    CONFIG.logo = e.target.result;
                    document.getElementById('logo-preview').innerHTML = '<div class="image-preview"><img src="' + e.target.result + '" alt="Logo"></div>';
                    document.getElementById('logo-upload-area').classList.add('has-image');
                    aplicarTema();
                };
                reader.readAsDataURL(input.files[0]);
            }
        }

        function aplicarTema() {
            document.documentElement.style.setProperty('--cor-primaria', CONFIG.corPrimaria);
            document.documentElement.style.setProperty('--cor-secundaria', CONFIG.corSecundaria);
            document.getElementById('nome-empresa').textContent = CONFIG.nomeEmpresa;
            
            if (CONFIG.logo) {
                document.getElementById('logo-display').innerHTML = '<img src="' + CONFIG.logo + '" alt="Logo">';
            } else {
                document.getElementById('logo-display').innerHTML = '<span class="logo-placeholder">🍕</span>';
            }
        }

        function alterarSenhaAdmin() {
            const novaSenha = document.getElementById('admin-nova-senha').value.trim();
            if (novaSenha.length < 4) {
                alert('⚠️ A senha deve ter pelo menos 4 caracteres!');
                return;
            }
            CONFIG.senhaAdmin = novaSenha;
            localStorage.setItem('config', JSON.stringify(CONFIG));
            alert('✅ Senha alterada com sucesso!');
            document.getElementById('admin-nova-senha').value = '';
        }

        function salvarConfiguracoes() {
            try {
                localStorage.setItem('config', JSON.stringify(CONFIG));
                alert('✅ Configurações salvas com sucesso!');
                aplicarTema();
            } catch (e) {
                alert('❌ Erro ao salvar configurações: ' + e.message);
            }
        }

        // Produtos Admin
        function abrirFormProduto(produtoId) {
            const modal = document.getElementById('form-produto-modal');
            const titulo = document.getElementById('form-produto-titulo');
            const idEdit = document.getElementById('produto-id-edit');

            if (produtoId) {
                const produto = PRODUTOS.find(function(p) { return p.id === produtoId; });
                if (!produto) {
                    alert('❌ Produto não encontrado!');
                    return;
                }
                titulo.textContent = '✏️ Editar Produto';
                idEdit.value = produtoId;
                document.getElementById('produto-nome').value = produto.nome;
                document.getElementById('produto-descricao').value = produto.descricao;
                document.getElementById('produto-preco').value = produto.preco;
                document.getElementById('produto-categoria').value = produto.categoria;
                document.getElementById('produto-imagem-data').value = produto.imagem || '';

                if (produto.imagem) {
                    document.getElementById('produto-image-preview').innerHTML = '<div class="image-preview"><img src="' + produto.imagem + '" alt="' + produto.nome + '"></div>';
                    document.getElementById('produto-image-upload-area').classList.add('has-image');
                }
            } else {
                titulo.textContent = '➕ Adicionar Produto';
                idEdit.value = '';
                limparFormProduto();
            }

            modal.classList.remove('hidden');
            document.body.style.overflow = 'hidden'; // Previne scroll
        }

        function fecharFormProduto() {
            const modal = document.getElementById('form-produto-modal');
            modal.classList.add('hidden');
            document.body.style.overflow = ''; // Restaura scroll
            limparFormProduto();
        }

        // Fechar modal ao clicar fora do conteúdo
        document.addEventListener('DOMContentLoaded', function() {
            const modals = document.querySelectorAll('.modal');
            modals.forEach(function(modal) {
                modal.addEventListener('click', function(e) {
                    if (e.target === modal) {
                        modal.classList.add('hidden');
                        document.body.style.overflow = ''; // Restaura scroll
                        if (modal.id === 'form-produto-modal') {
                            limparFormProduto();
                        } else if (modal.id === 'checkout-modal') {
                            limparFormularioCheckout();
                        }
                    }
                });
            });

            // Fechar modal com a tecla ESC
            document.addEventListener('keydown', function(e) {
                if (e.key === 'Escape') {
                    modals.forEach(function(modal) {
                        if (!modal.classList.contains('hidden')) {
                            modal.classList.add('hidden');
                            document.body.style.overflow = '';
                            if (modal.id === 'form-produto-modal') {
                                limparFormProduto();
                            } else if (modal.id === 'checkout-modal') {
                                limparFormularioCheckout();
                            }
                        }
                    });
                }
            });
        });

        function limparFormProduto() {
            document.getElementById('produto-nome').value = '';
            document.getElementById('produto-descricao').value = '';
            document.getElementById('produto-preco').value = '';
            document.getElementById('produto-categoria').value = '';
            document.getElementById('produto-imagem-file').value = '';
            document.getElementById('produto-imagem-data').value = '';
            document.getElementById('produto-id-edit').value = '';
            document.getElementById('produto-image-preview').innerHTML = '<div class="upload-icon">📸</div><div class="upload-text">Clique para fazer upload da imagem</div><div class="upload-hint">PNG, JPG ou GIF (max. 2MB)</div>';
            document.getElementById('produto-image-upload-area').classList.remove('has-image');
        }

        function carregarImagemProduto(input) {
            if (input.files && input.files[0]) {
                if (input.files[0].size > 2 * 1024 * 1024) {
                    alert('⚠️ A imagem deve ter no máximo 2MB');
                    return;
                }

                const reader = new FileReader();
                reader.onload = function(e) {
                    document.getElementById('produto-imagem-data').value = e.target.result;
                    document.getElementById('produto-image-preview').innerHTML = '<div class="image-preview"><img src="' + e.target.result + '" alt="Preview"></div>';
                    document.getElementById('produto-image-upload-area').classList.add('has-image');
                };
                reader.readAsDataURL(input.files[0]);
            }
        }

        function salvarProduto() {
            const nome = document.getElementById('produto-nome').value.trim();
            const descricao = document.getElementById('produto-descricao').value.trim();
            const preco = parseFloat(document.getElementById('produto-preco').value);
            const categoria = document.getElementById('produto-categoria').value.trim();
            const imagem = document.getElementById('produto-imagem-data').value;
            const idEdit = document.getElementById('produto-id-edit').value;

            if (!nome || !descricao || !preco || !categoria) {
                alert('⚠️ Preencha todos os campos obrigatórios!');
                return;
            }

            if (idEdit) {
                // Editar produto existente
                const produto = PRODUTOS.find(function(p) { return p.id == idEdit; });
                if (produto) {
                    produto.nome = nome;
                    produto.descricao = descricao;
                    produto.preco = preco;
                    produto.categoria = categoria;
                    produto.imagem = imagem;
                }
            } else {
                // Adicionar novo produto
                const novoId = Math.max.apply(Math, PRODUTOS.map(function(p) { return p.id; }).concat([0])) + 1;
                PRODUTOS.push({
                    id: novoId,
                    nome: nome,
                    descricao: descricao,
                    preco: preco,
                    categoria: categoria,
                    imagem: imagem
                });
            }

            salvarProdutos();
            fecharFormProduto();
            renderizarListaProdutosAdmin();
            renderizarProdutos();
            renderizarCategorias();
            atualizarEstatisticas();
            alert('✅ Produto salvo com sucesso!');
        }

        function removerProduto(id) {
            if (confirm('Tem certeza que deseja remover este produto?')) {
                PRODUTOS = PRODUTOS.filter(function(p) { return p.id !== id; });
                salvarProdutos();
                renderizarListaProdutosAdmin();
                renderizarProdutos();
                renderizarCategorias();
                atualizarEstatisticas();
            }
        }

        function renderizarListaProdutosAdmin() {
            const container = document.getElementById('lista-produtos-admin');
            
            if (PRODUTOS.length === 0) {
                container.innerHTML = '<div class="empty-cart"><div class="empty-cart-icon">📦</div><h3>Nenhum produto cadastrado</h3><p>Clique em "Adicionar Novo Produto" para começar</p></div>';
                return;
            }

            container.innerHTML = PRODUTOS.map(function(p) {
                const imagemHtml = p.imagem 
                    ? '<img src="' + p.imagem + '" alt="' + p.nome + '">' 
                    : '🍽️';
                
                return '<div class="product-admin-card">' +
                    '<div class="product-admin-image">' + imagemHtml + '</div>' +
                    '<div class="product-admin-info">' +
                        '<div class="product-admin-name">' + p.nome + '</div>' +
                        '<div class="product-admin-meta">' + p.categoria + ' • ' + p.descricao + '</div>' +
                        '<div class="product-admin-price">R$ ' + p.preco.toFixed(2) + '</div>' +
                    '</div>' +
                    '<div class="product-admin-actions">' +
                        '<button class="btn-edit" onclick="abrirFormProduto(' + p.id + ')">✏️ Editar</button>' +
                        '<button class="btn-delete" onclick="removerProduto(' + p.id + ')">🗑️ Remover</button>' +
                    '</div>' +
                '</div>';
            }).join('');
        }

        // LocalStorage
        function salvarCarrinho() {
            try {
                localStorage.setItem('carrinho', JSON.stringify(carrinho));
            } catch (e) {
                console.error('Erro ao salvar carrinho:', e);
            }
        }

        function carregarCarrinho() {
            try {
                const carrinhoSalvo = localStorage.getItem('carrinho');
                if (carrinhoSalvo) {
                    carrinho = JSON.parse(carrinhoSalvo);
                }
            } catch (e) {
                console.error('Erro ao carregar carrinho:', e);
                carrinho = [];
            }
        }

        function salvarProdutos() {
            try {
                localStorage.setItem('produtos', JSON.stringify(PRODUTOS));
            } catch (e) {
                console.error('Erro ao salvar produtos:', e);
            }
        }

        function carregarProdutos() {
            try {
                const produtosSalvos = localStorage.getItem('produtos');
                if (produtosSalvos) {
                    PRODUTOS = JSON.parse(produtosSalvos);
                }
            } catch (e) {
                console.error('Erro ao carregar produtos:', e);
            }
        }

        function carregarConfiguracoes() {
            try {
                const configSalva = localStorage.getItem('config');
                if (configSalva) {
                    CONFIG = JSON.parse(configSalva);
                }
            } catch (e) {
                console.error('Erro ao carregar configurações:', e);
            }
        }
    </script>
</body>
</html>
