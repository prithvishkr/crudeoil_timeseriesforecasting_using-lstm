# crudeoil_timeseriesforecasting_using-lstm
Lstm stands for long short term memory
this project is an implementation of timeseries forecasting using lstm

Stateful vs. Stateless LSTM
Stateless: LSTM updates parameters on batch 1 and then initiates cell states (meaning - memory, usually with zeros) for batch 2
Stateful: it uses batch 1 last output cell sates as initial states for batch 2.

When to use which?
When sequences in batches are related to each other (e.g. prices of one commodity), we should better use stateful mode
Else, when one sequence represents a complete sentence, we should go with stateless mode


Batch-size: which batch-size to choose?
Very important decision!

Imagine, you must learn to recognize a bird... You are presented images of different birds.

What would you prefer:

To see the one image at a time, make your notes about special bird quilities (set your weights) and then see another bird and so on
OR may be you would better learn if you see - let's say 5 - bird images at ones. May be then you can faster notice the bird's intrinsic properties?
I'd say - the second method is more efficient for humans. We need more examples of an entitiy, that we have to distinguish.

Batch-size and trainings-set size
With stateful LSTMs the trainings-set size must be divisible without remainder by the batch-size (modulo = 0)

How LSTM Param Number is computed?
To decide how to handle the memory each LSTM Cell has :

input (what to let in),

forget (what to forget) and

output (what to write to the output)

LSTM Cell State is its memory

LSTM Hidden State is equivalent to the Cell output:

lstm_hidden_state_size (number of neurons = memory cells) = lstm_outputs_size

Parameters:

weights for the inputs (lstm_inputs_size)

weights for the outputs (lstm_outputs_size)

bias variable

Result from previous point - for all 3 Gates and for Cell State ( = 4)
