#include <stdio.h>

/*function to insert an element into an array at specified position*/
void insert(int arr[100], int *size, int element, int pos)
{
	int i;
	for(i=*size-1; i>=pos; i--)
	{
		arr[i+1]=arr[i];
	}
	arr[pos-1]=element;
	(*size)++;
}

/*function to traverse the array and print it*/
void traverse(int arr[], int size)
{
	printf("Updated Array Elements: ");
	int i;
	for(i=0; i<size; i++)
	{
		printf("%2d", arr[i]);
		if(i<size-1)
		{
			printf(",");
		}
	}
	printf("\n");
}

/*function to update an element*/
void update(int arr[], int size, int element, int pos)
{
	arr[pos-1]=element;
}

/*function to Sort an Array Elements*/
void Sort(int arr[], int size)
{
	int i;
	for(i=1; i<size; i++)
	{
		int key=arr[i];
		int j=i-1;
		
		while(j>=0 && arr[j]>key)
		{
			arr[j+1]=arr[j];
			j--;
		}
		arr[j+1]=key;
	}
}

/*function to reverse an Array*/
void reverse(int arr[], int size)
{
  int i;
  for(i=size-1; i>=0; i--)
  {
	printf("%d\t", arr[i]);
  }
}

/*function to Delete an Element*/
void del(int arr[], int*size, int pos)
{
 int i;
 for(i=pos; i<*size-1; i++)
 {
  arr[i]=arr[i+1];	
 }
 (*size)--;
}

/*function to search an element*/
int search(int arr[], int size, int element)
{
	int i;
 for(i=0; i<size; i++)
 {
	if(arr[i]==element)
	{
		return i;
	}
 }
 return -1;
}

/*function to find the Smallest Element*/ 
int minimum(int arr[], int size)
{

int min = arr[0];
int i;
for(i=1; i<size; i++)
{
	if(arr[i]<min)
	{
		min = arr[i];
	}
}
return min;
}

/*function to find the Largest Element*/ 
int maximum(int arr[], int size)
{

int max = arr[0];
int i;
for(i=1; i<size; i++)
{
	if(arr[i]>max)
	{
		max = arr[i];
	}
}
return max;
}


int main()
{
	int arr[100], size, pos, element, i, min, max, choice, SearchResult;
	
	printf("👉 Enter the size of the array👈 =");
	scanf("%d", &size);
	
	printf("👾 Enter %d element👾️ : ", size);
	for(i=0; i<size; i++)
	{
     	scanf("%d", &arr[i]);
    }

    while(1)
    {
    	printf("~~~~~~~~~~~~~~~Welcome to the Array-Verse~~~~~~~~~~~~~~~\n");
    	printf("\n 👇 👇 👇 Select an Option👇 👇 👇 \n\n");
    	printf("Opt. 1:- Insert an Element📥\n");
    	printf("Opt. 2:- Update an Element📤 \n");
    	printf("Opt. 3:- Perform Sort of the Array 😵\n");
    	printf("Opt. 4:- Reverse the Array🤥\n");
    	printf("Opt. 5:- Delete an Element🥹\n");
    	printf("Opt. 6:- Search an Element🧐\n");
    	printf("Opt. 7:- Find the Minimum Element🫣\n");
    	printf("Opt. 8:- Find the Maximum Element🫣\n");
    	printf("Opt. 9:- Traverse the Array😌\n");
    	printf("Opt. 0:- Exit☠️\n");
		printf("                                      🫡 DHIRENDRA YADAV\n");
    	
        printf("Enter Your Choice: ");
    	scanf("%d", &choice);
    	
    	switch(choice)
    	{
		 case 1:
		    printf("Enter the element to Insert: ");
         	scanf("%d", &element);
	
	        printf("Enter the Position to Insert at: ");
	        scanf("%d", &pos);
	        
	        if(pos<0 || pos>size)
	        {
		     printf("Invalid Position for Insertion\n");
	        }
	        else
	        {
	         insert(arr, &size, element, pos);
            }
             if (pos>=0 && pos<=size)
            {
     	      traverse(arr, size);
	        }
	          printf("\n");
            printf("                                     🫡 DHIRENDRA YADAV\n");
            break;
        
		 case 2:    
		     printf("Enter the new element: ");
         	 scanf("%d", &element);
	         printf("Enter the Position to Update: ");
	         scanf("%d", &pos);	
	         update(arr, size, element, pos);
	         if (pos>=0 && pos<=size)
            {
     	      traverse(arr, size);
	        }
	        else
	        {
	        	printf("Invalid Position to Update\n");
			}
	         printf("\n");
	         printf("                                  🫡 DHIRENDRA YADAV\n");
	        break;
	        
	     case 3:
		    Sort(arr, size);
            traverse(arr, size);
            printf("Array Sorted Successfully\n");
            printf("\n");
            printf("                                      🫡 DHIRENDRA YADAV\n");
            break;
            
         case 4:
         	reverse(arr, size);
         	printf("\n");
         	printf("                                      🫡 DHIRENDRA YADAV\n");
         	break;
         
         case 5:
         	printf("Enter the Position to Delete from: ");
            scanf("%d", &pos);
    
            if(pos>=0 && pos<size)
            {
	         del(arr, &size, pos);
	         traverse(arr, size);
	        }
	        else
	        {
             printf("Invalid Position to Delete From");
         	}
         	printf("\n");
         	printf("                                      🫡 DHIRENDRA YADAV\n");
         	break;
         	
         case 6:
         	printf("Enter the element to Search for: ");
            scanf("%d", &element);
            SearchResult = search(arr, size, element);
            {
    	     if(SearchResult !=-1)
    	     {
    		  printf("Element found at position %d: %d\n", SearchResult, arr[SearchResult]);
		     }
		     else
		     {
			   printf("Element Not Found in the Array.\n");
		     }
	        }
	        printf("\n");
	        printf("                                      🫡 DHIRENDRA YADAV\n");
	        break;
	        
	     case 7:
	     	 min = minimum(arr, size);
             printf("The Smallest Element in the array : %d\n", min);
             printf("\n");
             break;
             
         case 8:
         	 max = maximum(arr, size);
             printf("The Largest Element in the array : %d\n", max);
             printf("\n");
             printf("                                      🫡 DHIRENDRA YADAV\n");
             break;
             
         case 9:
		      traverse(arr, size);
		      printf("\n");
		      printf("                                      🫡 DHIRENDRA YADAV\n");
			  break;    
		       
		 case 0:
		 	 return 0;
			  default:
			  printf("Invalid Option Selected. Please Try Again.\n");      
			  printf("*******🫡 🫡 🫡 *****THANK YOU****🫡 🫡 🫡 ****\n");
			  printf("\n");
			  break;
        }
    }
	return 0;
}
    
