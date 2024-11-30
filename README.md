#HomeWork5
class Person:
    def init(self, name, age):
        self.name = name
        self.age = age
    
    def greet(self):
        print(f"Hello, my name is {self.name}")

class Student(Person):
    def init(self, name, age, student_id):
        super().init(name, age)
        self.student_id = student_id
    
    def study(self):
        print("I'm studying!")

class Worker(Person):
    def init(self, name, age, position):
        super().init(name, age)
        self.position = position
    
    def work(self):
        print("I'm working!")


def inspect_class(cls): #Робив не сам:)
    print(f"\nAttributes of {cls.name}:")
    for attr in cls.dict:
        if not callable(getattr(cls, attr)) and not attr.startswith(""):
            print(f" - {attr}")
    

    print(f"\nMethods of {cls.__name}:")  #Робив не сам:)
    for method in cls.dict:
        if callable(getattr(cls, method)) and not method.startswith("__"):
            print(f" - {method}")


inspect_class(Student) #Інспекція класів
inspect_class(Worker)
