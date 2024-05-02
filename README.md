# Assignment Scheduler CLI

## Who Uses It?

High school and college students who struggle with managing their workload and meeting deadlines can benefit from using this tool.

## What?
Our project deals with that issue for you by organizing your courses and workload. It will create a custom work schedule (around your class schedule) based on how hard an assignment is, when it is due, how long it will take, etc etc… 

All features will be implemented using a CLI which can eventually be turned into a GUI for better visualization 

## Why?

For students, properly planning out a working strategy to complete their school work is a very strenuous task. Each day we are plagued with making thousands upon thousands of decisions, and the order in which we do our assignments shouldn’t have to be one of them. The lack of organization often leads to handing in assignments late, unnecessary stress, and inefficient use of time.

## How/Workflow

- Input Courses and Assignments: Users can input their courses for the semester along with corresponding assignments and due dates.
- Assign Priority Levels: The system assigns priority levels to each assignment based on factors such as due date, importance, complexity, and time required.
- Display Schedule: Generates a schedule displaying assignments in order of priority.
- Customization Options: Users can customize their priority schedule by adjusting priority levels, adding new assignments, removing completed tasks, and rearranging the schedule as needed.

## Classes

### Assignment Class

- **Instance Variables**:
  - `Course course`: Reference to an instance of Course Class.
  - `String name`: Name of the assignment.
  - `String description`: Description of the assignment.
  - `String startDate`: Date format of "dd-MM-yyyy HH:mm:ss".
  - `String dueDate`: Date format of "dd-MM-yyyy HH:mm:ss".
  - `int maxPoints`: Total possible assignment points.
  - `boolean isCompleted`: Did you finish the assignment yet.
  - `int estimatedTime`: How long will the assignment take to finish.
  - `int priority`: Algorithm gives score based off of various factors including dueDate, maxPoints, estimatedTime, Course.priority, Course.grade.
  - `AssignmentType type`: One of enum AssignmentType.

#### Enum: AssignmentType

- `Homework`
- `Test`
- `Quiz`
- `Project`

### Course Class

- **Instance Variables**:
  - `String name`: Name of the course.
  - `String subject`: Subject of the course.
  - `int grade`: Current grade in the course.
  - `int priority`: User assigned priority to the course, lower value means higher priority.

### ScheduleManager Class (Document-Store-esque)

- **Instance Variables**:
  - `Assignment[] assignments`: All assignments.
  - `Course[] courses`: All courses.
  - `PriorityQueue<Assignment> assignmentPriorityHeap`: Track priority of assignments.
  - `LinkedList<Assignment> assignmentChronology`: A list of all assignments sorted in order of assignment dueDate.
  - `HashMap<String, Assignment> assignmentMap`: Easy access to assignments by name.

## Data Structures

- **MaxHeap**: Maintains constant access to assignments with the highest priority as the upcoming assignment in the scheduler.
- **LinkedList**: Holds a chronological due date view of all assignments.
- **HashMap**: A direct access to assignments by name.
- **Arrays**: A storage to easily see all courses & assignments.
