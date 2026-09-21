Conectei o Power BI ao servidor do Azure Database for MySQL.
Selecionei o banco de dados azure_company.
Carreguei as seguintes tabelas no Power Query:
employee
departament
dependent
dept_locations
project
works_on
Renomeei as consultas:

________
Na tabela Employees, renomeei as colunas:
Ssn → Employee ID
Bdate → Employee Birth Date
Sex → Employee Gender
Super_ssn → Supervisor ID
Dno → Department ID
Removi a coluna Middle Initial.
Mesclei First Name e Last Name e renomeei Employee Name
Dividi a coluna Address em Street Number, Street Name, City e State
Substituí TX por Texas na coluna State.
Substituí Fire-Oak por Fire Oak

________

Na tabela Departments, renomeei as colunas:
Dname → Department Name
Dnumber → Department ID
Mgr_ssn → Manager ID
Mgr_start_date → Manager Start Date
Dept_create_date → Department Creation Date
________


Mesclei Employees com Departments utilizando:
Employees[Department ID]
Departments[Department ID]
Junção Externa esquerda
Expandi a coluna resultante da mesclagem.
Selecionei somente Department Name.

________
Na tabela Dependents, renomeei as colunas:
Essn → Employee ID
Dependent_name → Dependent Name
Sex → Dependent Gender
Bdate → Dependent Birth Date
Relationship → Relationship to Employee
________


Na tabela Department Locations, renomeei:
Dnumber → Department ID
Dlocation → Departm
Mesclei a tabela Department Locations com a tabela Departments.
Usei a coluna Department ID como chave de correspondência nas duas tabelas.
Selecionei a junção Externa esquerda
Expandi a coluna criada pela mesclagem.
Selecionei somente a coluna Department Name da tabela Departments.
Mesclei as colunas Department Name e Department Location.
Utilizei um espaço como separador entre os dois valores.
Renomeei a nova coluna resultante para Department Location.

________
Na tabela Projects, renomeei:
Pname → Project Name
Pnumber → Project ID
Plocation → Project Location
Dnum → Department ID
________
Na tabela Employee Projects, renomeei:
Essn → Employee ID
Pno → Project ID
Hours → Hours Worked
________


Mesclei Employees com Employees como nova consulta usando:
Employees[Employee ID]
Employees[Supervisor ID]
Junção Interna — Inner Join
Renomeei a nova consulta para Manager Employees.
Expandi a coluna resultante da mesclagem.
Organizei a tabela para apresentar:
Manager Name
Employee Name
Department Name
Department ID

________
Finalizei as transformações selecionando Fechar e aplicar.

