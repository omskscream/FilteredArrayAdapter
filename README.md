Filtered Array Adapter
======================

[*FilteredArrayAdapter*](/src/io/github/omskscream/android/widget/FilteredArrayAdapter.java "FilteredArrayAdapter.java") - ArrayAdapter with possibility of custom filtering of displaying items

```java
FilteredArrayAdapter<Teacher> teachersAdapter = 
        new FilteredArrayAdapter<Teacher>(this, 
                                        android.R.layout.simple_dropdown_item_1line,
                                        getAllTeachers()) 
    {
        @Override
        protected boolean isFilterCondition(final Teacher data, String constraint) {
            String lastName = data.getLastName().toLowerCase();
            String firstName = data.getFirstName().toLowerCase();
            String val = constraint.toLowerCase();
            if (nameL.contains(val) || nameF.contains(val) ) {
                return true;
            }
            return false;
        }
    };
```