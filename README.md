
class SBI:
    def __init__(self,Username,PIN,Balance):
        self.Uersname=Username
        self.PIP=PIN
        self.Balance=Balance
class Data(SBI):
    def __init__(self, Username, PIN, Balance):
        super().__init__(Username, PIN, Balance)
        Name=input("Enter Username..")
        if Name== Username:
            print(f"Wllcome.. {Name}")
            pin=int(input("Enter PIN..."))
            if pin==PIN:
                print(f"Balance: {Balance}")
            else:
                print("Wrong PIN.")
        else:
            print("Not AV.")  
class Amount_add(Data):
    def __init__(self, Username, PIN, Balance,Credit):
        super().__init__(Username, PIN, Balance)
        self.New_Balance=Credit+Balance
        print(f"Amount Credited Successfully! New Balance: {self.New_Balance}")
obj=Amount_add("Abhishek",123,1000,300)   

class System:
    def __init__(self,Name,ID):
        self.Name=Name
        self.__ID=ID
    def get(self):
        return self.__ID
class Data(System):
    def __init__(self, Name, ID,Specialization,shift):
        super().__init__(Name, ID)
        self.Specialization=Specialization
        self.shift=shift
    def systemm(self):
        print(f"Name: {self.Name} | Staf ID: {self.__ID} | Specialization: {self.Specialization} | Shift: {self.shift} ")
obj=Data("Abhishek","JN89237I","Machine Learning Enginiring","Day")
obj.systemm()

class Hospital_Management_System:
    def __init__(self,Doctor,Nurses, Receptionists,Lab_Technicians):
        self.Doctor=Doctor
        self.Nurses=Nurses
        self.Receptionists=Receptionists
        self.Lab_Technicians=Lab_Technicians

class staff_info(Hospital_Management_System):
    def __init__(self, Doctor, Nurses, Receptionists, Lab_Technicians,staff_ID,full_name,age,contect):
        super().__init__(Doctor, Nurses, Receptionists, Lab_Technicians)
        self.staff_ID=staff_ID
        self.full_name=full_name
        self.age=age
        self.contect=contect

class staff_info1(staff_info):
    def __init__(self, Doctor, Nurses, Receptionists, Lab_Technicians, staff_ID, full_name, age, contect,Doctor_specialization,nurse_ward,Lab_Technicians_specialization,):
        super().__init__(Doctor, Nurses, Receptionists, Lab_Technicians, staff_ID, full_name, age, contect)
        self.Doctor_specialization=Doctor_specialization
        self.nurse_ward=nurse_ward
        self.Lab_Technicians_specialization=Lab_Technicians_specialization
    def infomation(self):
        print(f"Doctor:{self.Doctor} | Nurses:{self.Nurses} | Reseptionists:{self.Receptionists} | Lab Technician:{self.Lab_Technicians} | Staff ID:{self.staff_ID} | Full Name:{self.full_name} | Age:{self.age} | Contect:{self.contect} | Doctor Specialization:{self.Doctor_specialization} | Nurse Ward:{self.nurse_ward} | Lab Technicians Specialization:{self.Lab_Technicians_specialization} ")
  
obj=staff_info1("Abhishek","Sanvi","Arvi","Aman","JHF484","Abhishek Malviy",20,9617595508,
                "Heart","ICU","Pharmacology",)
obj.infomation()
