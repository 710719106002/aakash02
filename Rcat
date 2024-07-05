#include<stdio.h>
#include<stdlib.h>
#include<string.h>

int main(int argc, char **argv) {
     FILE *fp;
     char ch;
     char word[100];
     int i = 0;

     if (argc!= 2) {
         printf("Invalid format\n");
         return 0;
     }

     fp = fopen(argv[1], "r+");
     if (fp == 0) {
         printf("File is not present\n");
         return 0;
     }

     fseek(fp, 0, SEEK_SET);

     while ((ch = fgetc(fp))!= EOF) {
         word[i++] = ch;
     }

     word[i] = '\0';

     // reverse the word
    int j, k;
     for (j = 0, k = strlen(word) - 1; j < k; j++, k--) {
         char temp = word[j];
         word[j] = word[k];
         word[k] = temp;
     }

     fseek(fp, 0, SEEK_SET);

     for (j = 0; j < strlen(word); j++) {
         fputc(word[j], fp);
     }

     fclose(fp);
     return 0;
 }
