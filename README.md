Filtered Array Adapter
======================

[*FilteredArrayAdapter*](/src/io/github/omskscream/android/widget/FilteredArrayAdapter.java "FilteredArrayAdapter.java") - ArrayAdapter with possibility of custom filtering of displaying items.
Was created for android.widget.AutoCompleteTextView, but may be used everywhere else.

Typical implementation might look like as shown:

```java
FilteredArrayAdapter<Teacher> teachersAdapter = 
        new FilteredArrayAdapter<Teacher>(this, 
                                        android.R.layout.simple_dropdown_item_1line,
                                        getAllTeachers()) 
    {
        @Override
        protected boolean isFilterCondition(final Teacher data, String constraint) {
            return data.getLastName().contains(constraint) 
                    || data.getFirstName().contains(constraint);
        }
    };
```