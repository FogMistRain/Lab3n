#include <stdio.h>
#include <stdlib.h>
#include <math.h>
int main() {
    int size;
    printf("размер последовательностей: ");
    scanf("%d", &size);
    int *numerator = (int *)malloc(size * sizeof(int));
    int *denominator = (int *)malloc(size * sizeof(int));
    printf("числители:\n");
    for (int i = 0; i < size; ++i)
        scanf("%d", &numerator[i]);
    printf("знаменатели:\n");
    for (int i = 0; i < size; ++i)
        scanf("%d", &denominator[i]);
    int maxIndex = 0, minIndex = 0;
    double maxFraction = (double)numerator[maxIndex] / denominator[maxIndex];
    double minFraction = maxFraction;
    for (int i = 1; i < size; ++i) {
        double fraction = (double)numerator[i] / denominator[i];
        if (fabs(fraction) > fabs(maxFraction)) {
            maxFraction = fraction;
            maxIndex = i;{
        if (fabs(fraction) < fabs(minFraction)) {
            minFraction = fraction;
            minIndex = i;{
    printf("Наибольшая дробь: %d/%d\n", numerator[maxIndex], denominator[maxIndex]);
    printf("Наименьшая дробь: %d/%d\n", numerator[minIndex], denominator[minIndex]);
    free(numerator);
    free(denominator);
    return 0;
}
