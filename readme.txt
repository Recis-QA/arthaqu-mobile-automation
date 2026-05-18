arthaqu-mobile-automation/
│
├── data/                            # 2. DATA FILES (Test Data & Envs)
│   ├── env/
│   │   ├── devel.yaml
│   │   └── prod.yaml
│   └── test_data/
│       ├── pulsa_data.yaml          # Data denom, nomor tujuan (misal: XL, Axis)
│       └── tagihan_data.yaml        # Data utilitas (misal: ID Pelanggan PLN, BPJS)
│
├── flows/                           # 1. TEST CASES (Skenario Utama)
│   ├── 01_onboarding/
│   │   ├── pos_login_success.yaml
│   │   └── neg_login_invalid_pwd.yaml
│   │
│   ├── 02_transaksi/
│   │   ├── pos_beli_paket_data.yaml
│   │   ├── pos_bayar_tagihan.yaml
│   │   └── neg_saldo_tidak_cukup.yaml
│   │
│   └── support/                     # Script Pendukung (Handlers)
│       ├── handle_landing_page.yaml
│       └── request_location_permission.yaml
│
└── subflows/                        # 3. KEYWORDS (Reusable Actions)
    ├── auth/
    │   ├── do_login.yaml
    │   └── do_logout.yaml
    └── security/
        └── input_pin.yaml           # Fungsi input PIN untuk transaksi