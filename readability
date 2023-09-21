#include <stdio.h>
#include <ctype.h>
#include <string.h>

int main(void)
{
    char text[10000];
    printf("Text: ");
    fgets(text, sizeof(text), stdin);

    int letters = 0;
    int words = 0;
    int sentences = 0;

    for (int i = 0, n = strlen(text); i < n; i++)
    {
        char c = text[i];

        if (isalpha(c))
        {
            letters++;
        }
        else if (isspace(c) && i > 0)
        {
            words++;
        }
        else if (c == '.' || c == '!' || c == '?')
        {
            sentences++;
        }
    }

    words++;  // Add one to words to account for the last word

    float L = (letters * 100.0) / words;
    float S = (sentences * 100.0) / words;

    int index = (int)(0.0588 * L - 0.296 * S - 15.8 + 0.5);

    if (index < 1)
    {
        printf("Before Grade 1\n");
    }
    else if (index >= 16)
    {
        printf("Grade 16+\n");
    }
    else
    {
        printf("Grade %i\n", index);
    }

    return 0;
}
