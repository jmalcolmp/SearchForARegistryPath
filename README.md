# SearchForARegistryPath
Search for a Registry Path for a specific Application using Python (winreg).


This script will set up five base keys to start searching from. These base keys are: HKEY_CLASSES_ROOT, HKEY_CURRENT_USER, HKEY_LOCAL_MACHINE, HKEY_USERS, and HKEY_CURRENT_CONFIG. 

It will then use a Breadth-First Search (BFS) to traverse the registry tree. 
This will begin a search at the root and explore all the neighbor nodes at the present depth prior to moving on to nodes at the next depth level.

For each key it checks, the script counts how many subkeys there are, using the QueryInfoKey function.

Then, for each of these subkeys, it tries to open the subkey and get its name.

If the name of the subkey matches the key you're looking for, it adds the full path of that subkey to a list of results.

Then regardless if it finds a match or not, it adds the subkey to the queue to be searched later.

It keeps doing this - checking each key in the queue, searching its subkeys, and adding them to the queue - until it's checked every key in the Windows registry.

Finally, it prints out the full paths of all the keys it found that match the name you're looking for.
