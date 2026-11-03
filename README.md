# Advanced Adder Designs for High-Performance Digital Circuits

Seminar by **Ekansh Bajpai** for *Topics in System Engineering – IC Design* (Topic 5: Arithmetic),
Winter 2024/25, Heinz Nixdorf Institut, Paderborn University.

Supervisor: Prof. Dr. Wolfgang Müller

| | |
|---|---|
| 📄 **Report** | [report/Seminar_Report_Ekansh_Bajpai.pdf](report/Seminar_Report_Ekansh_Bajpai.pdf) |
| 🎤 **Slides** | [presentation/Seminar_Presentation_Ekansh_Bajpai.pdf](presentation/Seminar_Presentation_Ekansh_Bajpai.pdf) |

## Abstract

AI and ML workloads increase the demand for high-performance digital circuits, meaning more speed, smaller area and lower power consumption. This report looks at adder circuits in digital electronics, especially how hierarchical and parallel computation reduce addition delay. It starts with the basics: binary addition, half adders, full adders and their CMOS implementations. It then covers generate-propagate logic and Manchester carry chains, followed by carry-bypass, carry-save and lookahead adders, with their performance trade-offs and critical-path delays. It ends with the advantages and disadvantages of each design and when one is preferred over another.

## Topics covered

| Adder | Idea | Critical-path delay |
|---|---|---|
| Ripple carry | Chain of full adders; each carry waits for the previous one | O(N) |
| Generate-propagate logic | Compute G = A·B and P = A⊕B up front; C<sub>out</sub> = G + P·C<sub>in</sub>, built as a Manchester carry chain | O(N), basis for faster designs |
| Carry bypass | Split into blocks of K bits; a multiplexer skips a block when all its bits propagate | O(N/K), with K<sub>opt</sub> = √(N·t<sub>mux</sub> / 2t<sub>carry</sub>) |
| Carry save | Compute each block for C<sub>in</sub> = 0 and 1 in parallel, then select; growing block sizes | O(√N) |
| Lookahead | Expand the carry recursion so all carries are computed in parallel; applied hierarchically to large adders | Ideally independent of N; in practice linear to quadratic due to gate fan-in, so used in blocks |

The basics section also covers binary addition, CMOS (pMOS/nMOS), half adders and full adders.

## Repository structure

```
.
├── README.md
├── report/
│   └── Seminar_Report_Ekansh_Bajpai.pdf          # 8-page report (IEEE format)
└── presentation/
    └── Seminar_Presentation_Ekansh_Bajpai.pdf    # 23 slides
```

## References

1. K. Abbas, "Arithmetic," in *Handbook of Digital CMOS Technology, Circuits, and Systems*, Springer, 2020, pp. 439–451. [doi:10.1007/978-3-030-37195-1_11](https://doi.org/10.1007/978-3-030-37195-1_11)
2. N. H. E. Weste and D. M. Harris, *CMOS VLSI Design: A Circuits and Systems Perspective*, 4th ed., Addison-Wesley, 2011.

Figures and tables in the report and slides are taken from these sources, as marked in each caption.

## License

© 2025 Ekansh Bajpai. All rights reserved unless stated otherwise. Figures from the referenced works belong to their respective copyright holders.
