# Repetition Codes for Bell-Pair Fidelity

Qiskit simulations behind two first-author papers on protecting shared entanglement. Alice and Bob each hold one qubit of a Bell pair sent over a noisy bit-flip channel. Each qubit is encoded in a quantum repetition code, errors are corrected from syndrome measurements, and the fidelity of the recovered Bell pair is compared with and without encoding.

## Notebooks

| Notebook | Contents |
| --- | --- |
| [`bit_flip_channel.ipynb`](bit_flip_channel.ipynb) | Fidelity of an unencoded Bell pair versus bit-flip probability, then with each half in a 3-qubit repetition code. Simulated fidelities are compared against closed-form expressions. |
| [`five_qubit_repetition.ipynb`](five_qubit_repetition.ipynb) | Extends the encoding to 5 qubits per half. Enumerates every X-error pattern on the 10 data qubits, counts which ones the code corrects, and builds the fidelity polynomial for no code, 3-qubit, and 5-qubit repetition. Includes a phase-flip circuit and a modified encoder. |
| [`same_error.ipynb`](same_error.ipynb) | Stabilizer view of the encoded Bell pair: tabulates the syndrome for every X or Z error on up to three qubits and checks which errors share a syndrome. |

## Papers

- S. E. U. Shubha, M. S. Rahman, and M. R. C. Mahdy, "Significant improvement of fidelity for encoded quantum Bell pairs at long and short-distance communication along with generalized circuit," *Heliyon*, vol. 9, no. 9, e19700, 2023. [DOI](https://doi.org/10.1016/j.heliyon.2023.e19700) · [PDF](JournalArticle.pdf)
- S. E. U. Shubha and M. S. Rahman, "Effect of quantum repetition code on fidelity of Bell states in bit flip channels," *12th International Conference on Electrical and Computer Engineering (ICECE)*, IEEE, pp. 368–371, 2022. [DOI](https://doi.org/10.1109/ICECE57408.2022.10088665) · [PDF](ConferencePaper.pdf)

## Run it

The notebooks use the pre-1.0 Qiskit API (`Aer`, `execute`), so pin the 0.46 line:

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt jupyter
jupyter notebook
```

The error-enumeration loops run thousands of small simulations, so a full run of `bit_flip_channel.ipynb` and `five_qubit_repetition.ipynb` takes several minutes.

## Author

[Syed Emad Uddin Shubha](https://syedshubha.com). Work done at Bangladesh University of Engineering and Technology (BUET) and North South University, 2022–2023.
