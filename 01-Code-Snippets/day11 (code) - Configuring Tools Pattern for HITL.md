
```Python
DANGEROUS_TOOL_NAMES = {"send_email", "delete_data", "execute_sql"}


def route_tools(state: State):
	# ... логика ...
	if any(name in DANGEROUS_TOOL_NAMES for name in tool_names):
		return "dangerous_tools"
	return "safe_tools"
```
