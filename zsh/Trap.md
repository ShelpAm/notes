To define the behavior of where a program get a signal, you can:
- execute `trap "$some_command" $some_signal`
- define a function named `TRAPXXX` where the `XXX` is name of the signal

For example, these are ok:
- `trap "echo I\'m trapped." INT`
- ```sh
	 TRAPINT() {
		 echo I\'m trapped.
	 }```

To unset a trap, use:
- `trap - $some_signal`
- or `unfunction $function_name`
It would not only remove the trap you set by 'trap xxx xxx', but also delete the function you set. So the former is preferred.