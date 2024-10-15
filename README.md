+-------------------+        +-------------------+         +-------------------+
|    Gymnasium      |1------>|     Session        |<-------2|      Coach         |
|-------------------|        |-------------------|         |-------------------|
| Gym_ID (PK)       |        | Session_ID (PK)    |         | Coach_ID (PK)      |
| Name              |        | Sport_Type         |         | Last_Name          |
| Address           |        | Schedule           |         | First_Name         |
| Phone_Number      |        | Max_Members (20)   |         | Age                |
+-------------------+        +-------------------+         | Specialty          |
                                                           +-------------------+

                                   |                                     ^
                                   | Many-to-Many                        | 
                                   | Registers                           | Leads
                                   |                                     |
                                   v                                     |

+-------------------+        +-------------------+
|     Member        |        |    Registers      |
|-------------------|        |-------------------|
| Member_ID (PK)    |        | Member_ID (FK)    |
| Last_Name         |        | Session_ID (FK)   |
| First_Name        |        +-------------------+
| Address           |
| Date_of_Birth     |
| Gender            |
+-------------------+

The ER diagram visually represents the entities, their attributes, and the relationships between them. Here's a guide to how the diagram for the gym management system should look:

ER Diagram Elements:
Entities: Represented by rectangles, each entity should include its attributes inside the rectangle.

Gymnasium: Attributes like Gym_ID, Name, Address, Phone_Number.
Member: Attributes like Member_ID, Last_Name, First_Name, Address, Date_of_Birth, Gender.
Session: Attributes like Session_ID, Sport_Type, Schedule, Max_Members.
Coach: Attributes like Coach_ID, Last_Name, First_Name, Age, Specialty.
Relationships: Represented by diamonds connecting entities with lines.

Offers: Between Gymnasium and Session (1 Gym offers many Sessions, 1 Session is offered by 1 Gym).
Registers: Between Member and Session (A Member registers for many Sessions, each Session has many Members).
Leads: Between Coach and Session (A Coach can lead many Sessions, each Session is led by up to 2 Coaches).
Cardinality: Defines the number of instances in a relationship.

1-to-many: For example, between Gymnasium and Session.
Many-to-many: For example, between Member and Session, Coach and Session.
Primary Keys: Underlined attributes, which uniquely identify each entity (e.g., Gym_ID, Member_ID, Session_ID, Coach_ID).
