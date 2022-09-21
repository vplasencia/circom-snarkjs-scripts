# Generic scripts using circom and snarkjs

To learn more about `circom`: <https://github.com/iden3/circom>

To learn more about `snarkjs`: <https://github.com/iden3/snarkjs>

The `circom compiler` version used is: `2.0.3`.

The `snarkjs` version used is: `0.4.19`.

To organize all the scripts you can create a `scripts` folder next to the circuit and input file you want to work with, and add all the scripts like this:

```text
├── scripts
│   ├── compile.sh
│   ├── executeGroth16.sh
│   ├── executePlonk.sh
│   ├── generateWitness.sh
│   ├── removeBuildFolder.sh
├── circuit.circom
├── input.json
```

When you wan to run a script, for each script:

Run the first time:

```bash
chmod u+x ./scripts/<scriptName>.sh
```

And after that, you can always run:

```bash
./scripts/<scriptName>.sh
```

When you run one of the circom or circom-snarkjs scripts, a build folder will be created with all the generated files inside. You can delete the build folder by running the `removeBuildFolder.sh` file.

```bash
./scripts/removeBuildFolder.sh
```

**Note:** It is not necessary to run the `removeBuildFolder.sh` script every time you want to run a new script, because every time you run a script, the build folder is automatically removed if it exists.

## circom scripts

- `compile.sh`

To compile circom circuits, you can run the `compile.sh` file.

```bash
./scripts/compile.sh
```

- `generateWitness.sh`

To generate the witness, you can run `generateWitness.sh`

```bash
./scripts/generateWitness.sh
```

When you run a circom script you will see something like this:

```text
├── build
│   ├── ...
├── scripts
│   ├── compile.sh
│   ├── executeGroth16.sh
│   ├── executePlonk.sh
│   ├── generateWitness.sh
│   ├── removeBuildFolder.sh
├── circuit.circom
├── input.json
```

## circom-snarkjs scripts

- `executeGroth16.sh`

To generate all the necessary files for a zero knowledge application using Groth16 run `executeGroth16.sh`.

```bash
./scripts/executeGroth16.sh
```

- `executePlonk.sh`

To generate all the necessary files for a zero knowledge application using Plonk run `executePlonk.sh`.

```bash
./scripts/executePlonk.sh
```

When you run one of the circom-snarkjs files, you will see something like this:

```text
├── build
│   ├── ...
├── ptau
│   ├── ...
├── scripts
│   ├── compile.sh
│   ├── executeGroth16.sh
│   ├── executePlonk.sh
│   ├── generateWitness.sh
│   ├── removeBuildFolder.sh
├── circuit.circom
├── input.json
```

**Note:** The `ptau` folder is generated with the necessary ptau file, but you can have this folder with the ptau that you will use, and it will not be generated again.

You can see different ptau files in the [snarkjs documentation](https://github.com/iden3/snarkjs#7-prepare-phase-2).
