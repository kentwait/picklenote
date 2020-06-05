# picklenote
Pickle an object together with a short note about it

## Quickstart
```python
import picklenote as pkl

data = [0, 1, 2, 3, 4]
note = "A list of 5 integers from 0"

# Dumps the object `data`, the annotation about the object `note`, and the filename where to save the pickle
pkl.dump(data, note, 'int_list.pickle')

# Loads the pickle as a PickleNote object with `.obj` and `.note` attributes
annotated_data = pkl.load('int_list.pickle')

# Returns the pickled object `[0, 1, 2, 3, 4]`
annotated_data.obj

# Returns the note:
#    A list of 5 integers from 0
annotated_data.note

# Can also be loaded using regular pickle
# Loads as a dictionary `{'obj': ..., 'note': ...}
import pickle

picklenote_dict = pickle.load(open('int_list.pickle', 'wb'))

```