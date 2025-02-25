## Submitting HTTP GET Requests for TSLA Orders

To achieve the objective of submitting HTTP GET requests to `https://example.com/api/:order_id` for Order IDs that are selling TSLA and writing the output to `./output.txt`, you can use a combination of command-line tools like `grep`, `jq`, `xargs`, and `curl`. Here's how you can do it in a single CLI command:

```bash
grep '"symbol": "TSLA"' ./transaction-log.txt | jq -r '.order_id' | xargs -I {} curl -s "https://example.com/api/{}" >> ./output.txt
```

### Explanation:

1. **`grep '"symbol": "TSLA"' ./transaction-log.txt`**: 
   - This filters the lines in `transaction-log.txt` that contain `"symbol": "TSLA"`, which are the orders selling TSLA.

2. **`jq -r '.order_id'`**:
   - This extracts the `order_id` from each JSON object.
   - The `-r` flag outputs raw strings (without quotes).

3. **`xargs -I {} curl -s "https://example.com/api/{}`"**:
   - This takes each `order_id` and substitutes it into the `curl` command.
   - The `-s` flag silences the progress output of `curl`.

4. **`>> ./output.txt`**:
   - This appends the output of each `curl` request to `output.txt`.
