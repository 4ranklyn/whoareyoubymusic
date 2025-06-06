graph TD
    A[Gambar Input] --> B(Model Scene Graph Generation);
    B --> C{Scene Graph Terstruktur (Objek, Atribut, Relasi)};
    C --> D[Konversi ke Teks Kontekstual];
    D --> E[Teks Konteks dari SGG];

    subgraph "Input untuk VLM"
        direction LR
        A_VLM(Gambar Input);
        E_VLM(Teks Konteks dari SGG);
        F[Instruksi Pengguna];
    end

    A_VLM --> G[Model VLM Pilihan (misal: LLaVA-1.5)];
    E_VLM --> G;
    F --> G;

    G --> H(Output: Paragraf Deskriptif yang Terpandu);

    style B fill:#f9f,stroke:#333,stroke-width:2px
    style G fill:#ccf,stroke:#333,stroke-width:2px
    style H fill:#9f9,stroke:#333,stroke-width:2px
