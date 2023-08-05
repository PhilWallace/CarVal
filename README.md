# CarVal
CarVal: Automated Attack Path Reasoning in IVN.

TD: URL -> Paper link.

## Rep Structure

Following files are the key of CarVal:

+ CarVal_Code
    + carval_infer.sh    <em>(Script to start infer attack path.)</em>
    + input_IVN.P  <em>(Input to CarVal, including the IVN and the attack goal to be inferred.)</em>
    + interaction_rules.P <em>(All interaction rules for CarVal reasoning.)</em>
    + risk_assessment.py <em>(This code will perform risk assessment based on the AttackGraph.dot generated by carval_infer.sh.)</em>


## Setup

CarVal is a tool for automatic attack path reasoning and risk assessment in modern in-vehicle network (IVN). 

1. Set up MulVal enviornment according to https://github.com/risksense/mulval.

2. Copy the CarVal code into the MulVal directory, including:

    * Replace <em>mulval/kb/interaction_rules.P</em> with <em>CarVal_Code/interaction_rules.P</em>

    * Copy all other codes under <em>CarVal_Code</em> (<em>carval_infer.sh, input_IVN.P, risk_assessment.py</em>) into <em>mulval/utils/</em>.

    * Now CarVal is ready to run. Execute the following code under the <em>mulval/utils</em>:

    ```
    ./carval_infer.sh -v ./input_IVN.P
    ```

    * Then the output attack path will be generated as <em>AttackGraph.dot</em> in the same directory. Then execute the python script to further calculate the risk values along the attack path.


    ```
    python risk_assessment.py
    ```


## An Example

![Risk Assessment Output](Example/risk_assess_output.png)












