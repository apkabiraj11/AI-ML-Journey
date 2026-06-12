# NumPy Notes

## Update Date:
- 12 June, 2026

#### Covered:
- Creating arrays (1D, 2D, zeros, ones, full, random, arange)
- Vector, Matrix, Tensor
- Array properties (shape, ndim, size, dtype)
- Reshaping (reshape, flatten, ravel, transpose)
- Indexing & slicing (1D, 2D, negative indexing)
- Sorting (1D and 2D with axis)
- Filtering (boolean filter, mask, np.where)
- Fancy indexing
- Adding & removing data (concatenate, vstack, hstack, delete)
- Mini project: Restaurant sales analysis

#### Key Concepts:
- NumPy is way faster than Python lists because it runs on C under the hood
- `flatten()` returns a copy, `ravel()` returns a view (no copy, faster)
- `axis=0` means operate down columns, `axis=1` means across rows
- `np.where(condition, if_true, if_false)` works like an if/else on arrays
- Boolean mask lets you store a condition and reuse it for filtering

#### Code Examples:
```python
# List vs NumPy
[1, 2, 3] * 2              # → [1, 2, 3, 1, 2, 3]  (repeats)
np.array([1, 2, 3]) * 2    # → [2, 4, 6]  (element-wise)

# Creating arrays
np.zeros((3, 4))
np.arange(0, 10, 2)        # [0, 2, 4, 6, 8]

# Slicing 2D
ar_2d[1, 2]    # specific element
ar_2d[1]       # entire row
ar_2d[:, 1]    # entire column

# np.where as if/else
np.where(numbers > 5, numbers * 2, numbers)

# vstack & hstack
np.vstack((matrix, new_row))   # add row
np.hstack((matrix, new_col))   # add column

# axis in action
np.sum(sales_data[:, 1:], axis=0)   # total per year
np.min(sales_data[:, 1:], axis=1)   # min per restaurant
```

#### What confused me & how I figured it out:
- `ravel` vs `flatten` — both give 1D but flatten makes a copy while ravel gives the original. So changing ravel output affects the original array.
- `axis=0` vs `axis=1` — kept mixing them up. Trick: axis=0 goes *down* (rows collapse), axis=1 goes *across* (columns collapse).

#### Summary in my own words:
NumPy is basically a supercharged list. Instead of looping through data manually, you can do operations on the whole array at once which is much faster. Today I learned how to create, reshape, slice, filter and modify arrays. The restaurant sales project tied everything together — using slicing to pick columns and axis to calculate totals and minimums across different directions.

---