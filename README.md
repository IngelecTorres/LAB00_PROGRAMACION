 # LAB00_PROGRAMACION
  Esta práctica de laboratorio se llevó a cabo con el fin de retomar las habilidades de programación en lenguaje C y aplicarlas al lenguaje de programación Python,  mediante el uso de sentencias cíclicas o de iteración, así mismo las sentencias de decisión; analizando cómo cambia la sintaxis de éstas en ambos lenguajes, aclarando conceptos como: bucles en un algoritmo y bloques de decisión. Se realizó el análisis de distintas situaciones que involucran la elaboración de algoritmos y su representación en diagramas de flujo y código en lenguaje C y Python, las cuales requerían repetir una acción y aplicar bucles adecuados, como: “for”, “while”, “If”,”else”, “elif”, obteniendo, como resultado, el conocimiento y experiencia acerca de cómo y en qué situaciones utilizar dichos ciclos en el lenguaje Python.

  # CODIGOS LAB 00
  Sentencias condicionales:
# Código en C:

	#include <stdio.h>

		float calcBmi(float h,float w);
		void range(float bmi); 


	int main(){

    float height;
    float weight;
    float bmi; 

    // Ask user for height in cms
    printf("Enter your height in cms: ");
    scanf("%f",&height); while (height<=0){printf("Enter your height in cms again: "); scanf("%f",&height);}

    // Ask user for weight in kgs
    printf("Enter your weight in kgs: ");
    scanf("%f",&weight); while (weight<=0){printf("Enter your weight in cms again: "); scanf("%f",&weight);}

    // Call calcBmi function
    bmi=calcBmi(height,weight);

    // Print result
    
    printf("Your body mass index is %f kg/m^2\n",bmi);
    range(bmi); } 


	float calcBmi(float h,float w){
    float bmi;

    // Compute body mass index
    bmi=w/((h/100.0)*(h/100.0));
    return bmi; }

		void range(float bmi){
		
        if (bmi<18.5){
            printf("your condition is low weight");
            }
        else if(bmi>=18.5 && bmi<25){
            printf("your condition is normal weight");
        } else if (bmi>=25 && bmi<30){
            printf("your condition is overweight");}
            else if (bmi>=30){
                printf("your condition is obesity");}
         else { printf("invalid condition");} 
        }
# Código en Python:
	def calcBmi(height,weight):
    
    bmi = float(weight/((height/100.0)*(height/100.0)))
        
    return bmi
	def Range(bmi2):
    
    if bmi2 < 18.5: 
        print("your condition is low weight")
    
    elif bmi2 >= 18.5 and bmi2 < 25: 
        print("your condition is normal weight")
    
    elif bmi2 >= 25 and bmi2 < 30: 
        print ("your condition is overweight")
    
    elif bmi2>=30:
        print("your condition is obesity")
    
    else: print("invalid condition")

	def main():

     height = float(input("Enter your height in cms: "))
     while height <= 0:
        height = float(input("Enter your height in cms again: "))
    										
    weight = float(input("Enter your weight in Kg: "))
    while weight <= 0:
        weight = float(input("Enter your weight in Kg again"))
    
    bmi = calcBmi(height, weight)
    print (f"Your body mass index is {bmi} kg/m^2\n")
    Range(bmi)
	if __name__ == "__main__":
    	main()
# Ciclos y arreglos
# Código en C:

    #include <stdio.h>
  	 void calcBmi(int number_people, float array[2][number_people]){
    float height, weight, bmi;
    float imc[number_people];
    for (int i=0; i<number_people; i++){
     height = array[0][i];
     weight = array[1][i];
     bmi = (weight/((height/100.0)*(height/100.0)));
     imc[i]=bmi;
     } 
    Range(number_people,imc); } 
		
  	void Range(int number_people, float imc_people_array[number_people]){
 
			float bmi2;
		 	int low_condition=0;
  		int normal_condition=0;
  		int overweight=0;
  		int obesity=0;
  		for (int i=0; i<number_people; i++){
    	bmi2=imc_people_array[i];
    if (bmi2 < 18.5){
       printf("The imc of person %d is %f\n", i+1, bmi2);
       low_condition+=1;}
    else if (bmi2 >= 18.5 && bmi2 < 25){ 
       printf("The imc of person %d is %f\n", i+1, bmi2);
       normal_condition+=1;}
    else if(bmi2 >= 25 && bmi2 < 30){
       printf("The imc of person %d is %f\n", i+1, bmi2);
       overweight+=1;}
    else if(bmi2>=30){
       printf("The imc of person %d is %f\n", i+1, bmi2);
       obesity+=1;}
    
    else{ printf("invalid condition");}
		
  	} 
	
  	percentage(low_condition,normal_condition,overweight,obesity,number_people);
  	}
  
    void percentage(int low, int normal,int over, int obesity, int number_people){
    float low_, normal_, over_, obesity_;
    low_= (((float)low/(float)number_people)*100);
    normal_ = (((normal*100)/number_people));
    over_ = (((float)over/(float)number_people)*100);
    obesity_ = (((float)obesity/(float)number_people)*100);
  
 	 printf("The percentage of people with low condition is: %.2f\n", low_);
 	 printf("The percentage of people with normal condition is: %.2f\n", normal_);
  	printf("The percentage of people with over condition is: %.2f\n", over_);
  	printf("The percentage of people with obesity condition is: %.2f\n", obesity_);
	}

	int main()
	{
    
    int number_people;
    float height, weight;
    
    printf("Please, write the number of people you want to calculate their bmi");
    scanf("%d", &number_people);
    float weight_and_height[2][number_people];
     while (height <=0) { }
    for (int i = 0; i < number_people; i++){
        printf("Enter the height of person %d on the list", i+1);
        scanf("%f", &height);
        while (height <=0) 
            {
            printf("Enter the height of person %d in cms again due to the number you recently entered isn't acceptable:  ", i+1);
            scanf("%f", &height); 
            } 
        printf("Enter the weight of person %d on the list", i+1);
        scanf("%f", &weight);
        while (weight<=0)
            {
            printf("Enter your weight in cms again due to the number you recently entered isn't acceptable:  ");
            scanf("%f", &weight);
            }
        weight_and_height[0][i]=height;
        weight_and_height[1][i]=weight;
		}

    calcBmi(number_people, weight_and_height);
  
  	}
	 
# Código en Python

	def calcBmi(number_people, array):
    imc=[]
    for i in range(number_people):
     height= array[i][0]
     weight= array[i][1]
     bmi = float(weight/((height/100.0)*(height/100.0)))
     imc.append(bmi)
    
    Range(imc,number_people)
    
	def Range(imc_people_array,number_people):
    
  	low_condition=0 
  	normal_condition=0
  	overweight=0
  	obesity=0
  	for i in range(number_people):
    bmi2 = imc_people_array[i]
    if bmi2 < 18.5: 
       print(f"The bmi of person {i+1} is {bmi2:.2f}")
       low_condition+=1
    elif bmi2 >= 18.5 and bmi2 < 25: 
       print(f"The bmi of person {i+1} is {bmi2:.2f}")
       normal_condition+=1
    elif bmi2 >= 25 and bmi2 < 30: 
       print(f"The bmi of person {i+1} is {bmi2:.2f}")
       overweight+=1
    elif bmi2>=30:
       print(f"The bmi of person {i+1} is {bmi2:.2f}")
       obesity+=1
    
    else: print("invalid condition")
    percentage(low_condition,normal_condition,overweight,obesity,number_people)

	def percentage(low,normal,over,obesity,number_people):
  	low = ((low/number_people)*100)
  	normal = ((normal/number_people)*100)
  	over = ((over/number_people)*100)
  	obesity = ((obesity/number_people)*100)
  
  	print(f"The percentage of people with low condition is {low:.0f}%")
  	print(f"The percentage of people with normal condition is {normal:.0f}%")
  	print(f"The percentage of people with overweight is {over:.0f}%")
  	print(f"The percentage of people with obesity is {obesity:.0f}%")
	def main():
    
  	number_people = int(input("Please, write the number of people you want to calculate their bmi:  "));
	
  	while number_people  <= 0:
     number_people = int(input("Enter a number of people correctly, because the one you recently enter isn't acceptable:   "));  
 	 weight_and_height = [];
  	for i in range(number_people):
    height=float(input(f"Enter the height in cms of person {i+1} on the list:  "));
    while height  <= 0:
     height = float(input("Enter the height in cms again due to the number you recently entered isn't acceptable:   "));  
      
    weight = float(input(f"Enter the weight in kg of person {i+1} on the list:  "));
    while weight <= 0:
      weight = float(input("Enter your weight in kg again due to the number you recently entered isn't acceptable:  "));
        
    weight_and_height.append([height,weight]);
    
 	 calcBmi(number_people, weight_and_height)

	if __name__ == "__main__":
   	 main()

# Funciones 
 # Código en Python

	def calc_bmi(h, w):
    
    bmi = w / ((h / 100.0) * (h / 100.0))
    return bmi


	def calculate_ideal_weight(h):
    # Calcular el rango de peso ideal para un BMI normal (18.5 - 24.9)
    min_normal_weight = 18.5 * ((h / 100.0) * (h / 100.0))
    max_normal_weight = 24.9 * ((h / 100.0) * (h / 100.0))
    return min_normal_weight, max_normal_weight


	def range_bmi(bmi, height):
    if bmi < 18.5:
        print("Your condition is low weight")
        min_weight, max_weight = calculate_ideal_weight(height)
        print(f"To reach a normal weight, your weight should be between {min_weight:.2f} kg and {max_weight:.2f} kg.")
    elif 18.5 <= bmi < 25:
        print("Your condition is normal weight")
    elif 25 <= bmi < 30:
        print("Your condition is overweight")
        min_weight, max_weight = calculate_ideal_weight(height)
        print(f"To reach a normal weight, your weight should be between {min_weight:.2f} kg and {max_weight:.2f} kg.")
    elif bmi >= 30:
        print("Your condition is obesity")
        min_weight, max_weight = calculate_ideal_weight(height)
        print(f"To reach a normal weight, your weight should be between {min_weight:.2f} kg and {max_weight:.2f} kg.")
    else:
        print("Invalid condition")


	def main():
    
    height = float(input("Enter your height in cms: "))
    while height <= 0:
        height = float(input("Enter your height in cms again: "))

   
    weight = float(input("Enter your weight in kgs: "))
    while weight <= 0:
        weight = float(input("Enter your weight in kgs again: "))

    
    bmi = calc_bmi(height, weight)

    
    print(f"Your body mass index is {bmi:.2f} kg/m^2")
    range_bmi(bmi, height)

	if __name__ == "__main__":
    main()
