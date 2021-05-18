#include <stdio.h>
#include <stdlib.h>
#include <string.h>
 char** temp;
int lexicographic_sort(const char* a, const char* b) {

return strcmp(a,b);
     
}

// int lexicographic_sort_reverse(const char* a, const char* b) {

// }

// int sort_by_number_of_distinct_characters(const char* a, const char* b) {
    
// }

// int sort_by_length(const char* a, const char* b) {

// }

void string_sort(char** arr,const int len,int (*cmp_func)(const char* a, const char* b)){
   
    char temp[len];
    if(cmp_func==lexicographic_sort)
    { 
    for(int i=0;i<len-1;i++) 
    { 
        for(int j=i+1;j<len;j++)
        {   
            printf("\n\n\n\n\nFor i=%d and j=%d \n\narr[%d]=%s and arr[%d]=%s\n ",i,j,i,arr[i],j,arr[j]);
            int returned = lexicographic_sort(arr[i],arr[j]);
            if(returned>0)
            {
                strcpy(temp,arr[i]);
                strcpy(arr[i],arr[j]);
                strcpy(arr[j],temp);
                
            }
            
            printf(" now after using the function \na[%d]=%s and arr[%d]=%s\n",i,arr[i],j,arr[j]);
        }
        
    }
   
}}


int main() 
{
    int n;
    scanf("%d", &n);
  
    char** arr;
	arr = (char**)malloc(n * sizeof(char*));
  
    for(int i = 0; i < n; i++){
        *(arr + i) = malloc(1024 * sizeof(char));
        scanf("%s", *(arr + i));
        *(arr + i) = realloc(*(arr + i), strlen(*(arr + i)) + 1);
    }
  
    string_sort(arr, n, lexicographic_sort);
    for(int i = 0; i < n; i++)
        printf("%s\n", arr[i]);
    printf("\n");

    // string_sort(arr, n, lexicographic_sort_reverse);
    // for(int i = 0; i < n; i++)
    //     printf("%s\n", arr[i]); 
    // printf("\n");

    // string_sort(arr, n, sort_by_length);
    // for(int i = 0; i < n; i++)
    //     printf("%s\n", arr[i]);    
    // printf("\n");

    // string_sort(arr, n, sort_by_number_of_distinct_characters);
    // for(int i = 0; i < n; i++)
    //     printf("%s\n", arr[i]); 
    // printf("\n");
}
