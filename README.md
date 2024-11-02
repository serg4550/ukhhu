print('Lesson 3: Work with several classes\n')

class StudySubject:
    def __init__(self, name: str, hours: int, level: str):
        self.name = name
        self.hours = hours
        self.level = level
        
    def __str__(self):
        return f'{self.name} {self.level}, кількість годин {self.hours}'

class Group:
    def __init__(self, teacher_name: str, days: list):
        self.teacher_name = teacher_name
        self.days = days
        
    def __str__(self):
        days_str = ', '.join(self.days)
        return f'Викладач: {self.teacher_name}, Дні занять: {days_str}'

class Student:
    def __init__(self, second_name: str, first_name: str, age: int, study_subject: StudySubject, group: Group, is_offline=True):
        self.first_name = first_name
        self.second_name = second_name
        self.age = age
        self.is_offline = is_offline
        self.study_subject = study_subject
        self.group = group
        
    def __str__(self):
        study_type = 'offline' if self.is_offline else 'online'
        student_info = f'{self.second_name} {self.first_name}, вік {self.age}, навчається {study_type}'
        return f'{student_info}\n{self.study_subject}\n{self.group}'

# Create a StudySubject
py_senior = StudySubject('Python', 18, 'Senior')

# Create a Group
python_group = Group('Олександр Іванов', ['Понеділок', 'Середа', 'П’ятниця'])

# Create a Student
DushlyukMakar = Student('Дишлюк', "Макар", 13, py_senior, python_group)

# Print student information
print(DushlyukMakar)
