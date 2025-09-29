# ContosoUniversity

Week 6
The database has been migrated and the database recreated to match the new data model. This create a database for the project specified by school context. The Student entity has been edited to include a FullName property, which is a result of concatenating the properties of FirstName and LastName. The DataType attribute has been changed to only showing the date and excluding the time. OfficeAssignment model entity has been created with a property to hold a single OfficeAssignment entity that may be null. The course model entity was updated with a foreign key property of DepartmentID that points to the Department entity. Then, school context was updated to include these new models of Department, Instructors, and OfficeAssignments. New information was seeded in DbInitializer. We drop and update the database using EF Core by deleting the Migrations folder, dropping the database, adding the migration of the InitialCreate sample data, and updating the database. The Courses pages was scaffolded and displays the Name property of the Department entity instead of the DepartmentID, correctly showing 'Mathematics' instead of a number. Create, read(details), edit, and delete functions were added to the Courses page. Similarly, the Instructors page was scaffolded and shows data from the 3 tables of Instructors, Courses, and Enrollments through a view model. When retrieving this data, it eager loads the Instructor navigation properties and other tables as needed. In Courses create/edit pages, a SelectList is used to select the department in a dropdown list with department names instead of ids, deriving from DepartmentNamePageModel. The instructor create/edit page has been updated to include checkboxes for the course objects through the view model AssignedCourseData. This view model contains the CourseID, title, and assigned boolean. Method PopulateAssignedCourseData in base class InstructorCoursesPageModel for edit/create in Courses will read all of the Course entities and populate AssignedCourseDataList through a HashSet. 
Unfortunately, I was unable to create a working project for seeding the data into an XML file.


Week 5
Test Plan: 
Select the Students tab. Observe the pagination view of only 3 students at a time. This shows the read data in CRUD.
Select the LastName and EnrollmentDate filters for sorting.
In the search bar, enter 'Peggy' and select [Search] to find Peggy Justice.
Select [Edit] next to Peggy to edit their enrollmentdate to the year of '2017'. Select [Save].
Search for Peggy once more, and observe the updated EnrollmentDate of 9/1/2017. This shows proper updating in CRUD.
Select Details to view details.
Select [Back to List].
Select [Create New] and enter test information. This will demonstrate creating in CRUD.
Search your created student. The entry will appear.
Delete the student by selecting [Delete]. Confirm by selecting [Delete] again. This will demonstrate deleting in CRUD.
Attempt to search the created student. The student will not appear and is properly deleted.
