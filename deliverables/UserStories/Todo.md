## Table of Contents

## Todo
- [Home](../../README.md)
- [Expectations](#expectations)
- [Acceptance Criteria](#acceptance-criteria)
    - [Creating a Todo](#creating-a-todo)
    - [Creating New Categories](#creating-new-categories)
    - [Updating the Date and Time of a Todo](#updating-the-date-and-time-of-a-todo)
    - [Filtering Todos](#filtering-todos)
    - [Deleting Todos](#deleting-todos)
    - [Additional Acceptance Criteria](#additional-acceptance-criteria)


## [Expectations](#table-of-contents)
- As an `authenticated user` `I want to` create a todo with some content, category, time, and date `so that` I can keep a list of my tasks.
- As an `authenticated user` `I want to` create new categories `so that` I can diversify my todos.
- As an `authenticated user` `I want to` be able to update the date and time of my todo `so that` I can move deadlines.
- As an `authenticated user` `I want to` filter my Todos by date, time, category, and text `so that` I do not have to scroll forever. 
- As an `authenticated user` `I want to` change my password `so that` if I forget it or want to keep my account secure I can. 
- As an `authenticated user` `I want to` delete my Todos `so that` I can keep my list of Todos lean and relevant.

### [Acceptance Criteria](#table-of-contents)

#### [Creating a Todo](#table-of-contents)
- The user must be able to create a todo with a title, content, category, date, and time.
- The title and content fields should not be empty.
- The category field should allow the user to select from existing categories or add a new category.
- The date and time fields should accept valid date and time formats.
- A confirmation message should be displayed upon successful creation of a todo.
- The new todo should appear in the list of todos immediately after creation.

#### [Creating New Categories](#table-of-contents)
- The user should be able to add a new category by entering a category name.
- The category name should not be empty and should be unique.
- A confirmation message should be displayed upon successful creation of a new category.
- The new category should be available in the category selection dropdown when creating or editing todos.

#### [Updating the Date and Time of a Todo](#table-of-contents)
- The user must be able to update the date and time of an existing todo.
- The date and time fields should accept valid date and time formats.
- A confirmation message should be displayed upon successful update.
- The updated todo should reflect the new date and time in the list of todos.

#### [Filtering Todos](#table-of-contents)
- The user must be able to filter todos by date, time, category, and text.
- The filter options should be easily accessible and intuitive to use.
- Applying a filter should update the list of todos to show only those that match the filter criteria.
- Clearing a filter should return the full list of todos.

#### [Deleting Todos](#table-of-contents)
- The user must be able to delete a todo.
- A confirmation prompt should be displayed before the todo is deleted.
- Upon confirmation, the todo should be removed from the list of todos.
- A confirmation message should be displayed upon successful deletion.

#### [Additional Acceptance Criteria](#table-of-contents)
- Error Handling: Appropriate error messages should be displayed for invalid inputs or actions that cannot be completed.
- Performance: The application should perform actions (create, update, delete, filter) quickly and efficiently.
- Security: All user actions should be authenticated, ensuring only the logged-in user can modify their todos.
- Usability: The UI should be user-friendly and accessible, with intuitive navigation and clear instructions.