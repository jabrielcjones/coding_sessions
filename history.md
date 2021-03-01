1. Get timestamp - YYYY-MM-DD_HH_MM_SS
2. Do your typical processing
3. Build Execution Record (dict)

	execution_record = build_exection_record(timestamp, input1, inputN, output1, outputN)

		Execution Record

		execution_record = {
			"timestamp": "timestamp",
			"input": 
				{
					"input1": "input1",
					"inputN": "inputN"
				},
			"output":
				{
					"output1": "output1",
					"outputN": "outputN"
				}
		}

4. Check for history.json (check_history())

	if exists

		1. Read it in as dict 

			read_history()

			history_dict = read_history()

		// 2. Add the new execution record to the history dict (add_execution_record(history_dict, execution_record))

		// 	history_dict['executionHistory'].append(new_execution)

		// 3. Write the history dict to history.json (write_history(history_dict))

	if don't exists

		1. Create the history dict 

			create_history()

				history_dict = {
					"executionHistory": []
				}

			history_dict = create_history()

5. Add the new execution record to the history dict 

	history_dict = add_execution_record(history_dict, execution_record)

		history_dict['executionHistory'].append(new_execution)

6. Write the history dict to history.json (write_history(history_dict))




Execution History (history.json)

{
	"executionHistory": [
		{
			"timestamp": "timestamp",
			"input": 
				{
					"input1": "input1",
					"inputN": "inputN"
				},
			"output":
				{
					"output1": "output1",
					"outputN": "outputN"
				}
		},
		{
			"timestamp": "timestamp",
			"input": 
				{
					"input1": "input1",
					"inputN": "inputN"
				},
			"output":
				{
					"output1": "output1",
					"outputN": "outputN"
				}
		}
	]
}