# Text manipulation with Linux
## Exercises 

1. Search all sequences containing "Loxondota" in ``/home/student/lorem.txt``
    > Flag : ``BC{GREP_ME_LOREM_FL4G}``
1. Copy the file /etc/passwd to your home directory. Display the line starting with ``student`` name.
    > Your commands :
    ```
    grep ^student passwd
    ```
1. Display the lines in the passwd file starting with login names of 3 or 4 characters.
    > Your commands :
    ```
    grep -E "^[a-zA-Z]{3,4}:" passwd
    ```
1. In the file ``/home/student/sample.txt`` how many different values are there in the first column? in the second?
    > Your response : 4 and 4

    > Your command :
    ```
    cut -d "," -f 1 sample.txt | sort -u | wc -l
    cut -d "," -f 2 sample.txt | sort -u | wc -l
    ```
1. In the file ``/home/student/sample.txt`` sort the values in the second column by frequency of occurrence. (uniq -c can be useful)
    > Your response :  
    ```
      1 11
      1 30
      2 10
      4 20
    ```
    > Your command :
    ```
    cut -d "," -f 2 sample.txt | sort | uniq -c | sort
    ```
1. In the file ``/home/student/iris.data`` Change the column separator (comma) to tab (make sure that the changes are applied to the file)
    > Your response :  
    ```
    5.1	3.5	1.4	0.2	Iris-setosa
    4.9	3.0	1.4	0.2	Iris-setosa
    4.7	3.2	1.3	0.2	Iris-setosa
    4.6	3.1	1.5	0.2	Iris-setosa
    5.0	3.6	1.4	0.2	Iris-setosa
    5.4	3.9	1.7	0.4	Iris-setosa
    4.6	3.4	1.4	0.3	Iris-setosa
    5.0	3.4	1.5	0.2	Iris-setosa
    4.4	2.9	1.4	0.2	Iris-setosa
    4.9	3.1	1.5	0.1	Iris-setosa
    5.4	3.7	1.5	0.2	Iris-setosa
    4.8	3.4	1.6	0.2	Iris-setosa
    4.8	3.0	1.4	0.1	Iris-setosa
    4.3	3.0	1.1	0.1	Iris-setosa
    5.8	4.0	1.2	0.2	Iris-setosa
    5.7	4.4	1.5	0.4	Iris-setosa
    5.4	3.9	1.3	0.4	Iris-setosa
    5.1	3.5	1.4	0.3	Iris-setosa
    5.7	3.8	1.7	0.3	Iris-setosa
    5.1	3.8	1.5	0.3	Iris-setosa
    5.4	3.4	1.7	0.2	Iris-setosa
    5.1	3.7	1.5	0.4	Iris-setosa
    4.6	3.6	1.0	0.2	Iris-setosa
    5.1	3.3	1.7	0.5	Iris-setosa
    4.8	3.4	1.9	0.2	Iris-setosa
    5.0	3.0	1.6	0.2	Iris-setosa
    5.0	3.4	1.6	0.4	Iris-setosa
    5.2	3.5	1.5	0.2	Iris-setosa
    5.2	3.4	1.4	0.2	Iris-setosa
    4.7	3.2	1.6	0.2	Iris-setosa
    4.8	3.1	1.6	0.2	Iris-setosa
    5.4	3.4	1.5	0.4	Iris-setosa
    5.2	4.1	1.5	0.1	Iris-setosa
    5.5	4.2	1.4	0.2	Iris-setosa
    4.9	3.1	1.5	0.1	Iris-setosa
    5.0	3.2	1.2	0.2	Iris-setosa
    5.5	3.5	1.3	0.2	Iris-setosa
    4.9	3.1	1.5	0.1	Iris-setosa
    4.4	3.0	1.3	0.2	Iris-setosa
    5.1	3.4	1.5	0.2	Iris-setosa
    5.0	3.5	1.3	0.3	Iris-setosa
    4.5	2.3	1.3	0.3	Iris-setosa
    4.4	3.2	1.3	0.2	Iris-setosa
    5.0	3.5	1.6	0.6	Iris-setosa
    5.1	3.8	1.9	0.4	Iris-setosa
    4.8	3.0	1.4	0.3	Iris-setosa
    5.1	3.8	1.6	0.2	Iris-setosa
    4.6	3.2	1.4	0.2	Iris-setosa
    5.3	3.7	1.5	0.2	Iris-setosa
    5.0	3.3	1.4	0.2	Iris-setosa
    7.0	3.2	4.7	1.4	Iris-versicolor
    6.4	3.2	4.5	1.5	Iris-versicolor
    6.9	3.1	4.9	1.5	Iris-versicolor
    5.5	2.3	4.0	1.3	Iris-versicolor
    6.5	2.8	4.6	1.5	Iris-versicolor
    5.7	2.8	4.5	1.3	Iris-versicolor
    6.3	3.3	4.7	1.6	Iris-versicolor
    4.9	2.4	3.3	1.0	Iris-versicolor
    6.6	2.9	4.6	1.3	Iris-versicolor
    5.2	2.7	3.9	1.4	Iris-versicolor
    5.0	2.0	3.5	1.0	Iris-versicolor
    5.9	3.0	4.2	1.5	Iris-versicolor
    6.0	2.2	4.0	1.0	Iris-versicolor
    6.1	2.9	4.7	1.4	Iris-versicolor
    5.6	2.9	3.6	1.3	Iris-versicolor
    6.7	3.1	4.4	1.4	Iris-versicolor
    5.6	3.0	4.5	1.5	Iris-versicolor
    5.8	2.7	4.1	1.0	Iris-versicolor
    6.2	2.2	4.5	1.5	Iris-versicolor
    5.6	2.5	3.9	1.1	Iris-versicolor
    5.9	3.2	4.8	1.8	Iris-versicolor
    6.1	2.8	4.0	1.3	Iris-versicolor
    6.3	2.5	4.9	1.5	Iris-versicolor
    6.1	2.8	4.7	1.2	Iris-versicolor
    6.4	2.9	4.3	1.3	Iris-versicolor
    6.6	3.0	4.4	1.4	Iris-versicolor
    6.8	2.8	4.8	1.4	Iris-versicolor
    6.7	3.0	5.0	1.7	Iris-versicolor
    6.0	2.9	4.5	1.5	Iris-versicolor
    5.7	2.6	3.5	1.0	Iris-versicolor
    5.5	2.4	3.8	1.1	Iris-versicolor
    5.5	2.4	3.7	1.0	Iris-versicolor
    5.8	2.7	3.9	1.2	Iris-versicolor
    6.0	2.7	5.1	1.6	Iris-versicolor
    5.4	3.0	4.5	1.5	Iris-versicolor
    6.0	3.4	4.5	1.6	Iris-versicolor
    6.7	3.1	4.7	1.5	Iris-versicolor
    6.3	2.3	4.4	1.3	Iris-versicolor
    5.6	3.0	4.1	1.3	Iris-versicolor
    5.5	2.5	4.0	1.3	Iris-versicolor
    5.5	2.6	4.4	1.2	Iris-versicolor
    6.1	3.0	4.6	1.4	Iris-versicolor
    5.8	2.6	4.0	1.2	Iris-versicolor
    5.0	2.3	3.3	1.0	Iris-versicolor
    5.6	2.7	4.2	1.3	Iris-versicolor
    5.7	3.0	4.2	1.2	Iris-versicolor
    5.7	2.9	4.2	1.3	Iris-versicolor
    6.2	2.9	4.3	1.3	Iris-versicolor
    5.1	2.5	3.0	1.1	Iris-versicolor
    5.7	2.8	4.1	1.3	Iris-versicolor
    7.0	3.2	4.7	1.4	Iris-versicolor
    6.4	3.2	4.5	1.5	Iris-versicolor
    6.9	3.1	4.9	1.5	Iris-versicolor
    5.5	2.3	4.0	1.3	Iris-versicolor
    6.5	2.8	4.6	1.5	Iris-versicolor
    5.7	2.8	4.5	1.3	Iris-versicolor
    6.3	3.3	4.7	1.6	Iris-versicolor
    4.9	2.4	3.3	1.0	Iris-versicolor
    6.6	2.9	4.6	1.3	Iris-versicolor
    5.2	2.7	3.9	1.4	Iris-versicolor
    5.0	2.0	3.5	1.0	Iris-versicolor
    5.9	3.0	4.2	1.5	Iris-versicolor
    6.0	2.2	4.0	1.0	Iris-versicolor
    6.1	2.9	4.7	1.4	Iris-versicolor
    5.6	2.9	3.6	1.3	Iris-versicolor
    6.7	3.1	4.4	1.4	Iris-versicolor
    5.6	3.0	4.5	1.5	Iris-versicolor
    5.8	2.7	4.1	1.0	Iris-versicolor
    6.2	2.2	4.5	1.5	Iris-versicolor
    5.6	2.5	3.9	1.1	Iris-versicolor
    5.9	3.2	4.8	1.8	Iris-versicolor
    6.1	2.8	4.0	1.3	Iris-versicolor
    6.3	2.5	4.9	1.5	Iris-versicolor
    6.1	2.8	4.7	1.2	Iris-versicolor
    6.4	2.9	4.3	1.3	Iris-versicolor
    6.6	3.0	4.4	1.4	Iris-versicolor
    6.8	2.8	4.8	1.4	Iris-versicolor
    6.7	3.0	5.0	1.7	Iris-versicolor
    6.0	2.9	4.5	1.5	Iris-versicolor
    5.7	2.6	3.5	1.0	Iris-versicolor
    5.5	2.4	3.8	1.1	Iris-versicolor
    5.5	2.4	3.7	1.0	Iris-versicolor
    5.8	2.7	3.9	1.2	Iris-versicolor
    6.0	2.7	5.1	1.6	Iris-versicolor
    5.4	3.0	4.5	1.5	Iris-versicolor
    6.0	3.4	4.5	1.6	Iris-versicolor
    6.7	3.1	4.7	1.5	Iris-versicolor
    6.3	2.3	4.4	1.3	Iris-versicolor
    5.6	3.0	4.1	1.3	Iris-versicolor
    5.5	2.5	4.0	1.3	Iris-versicolor
    5.5	2.6	4.4	1.2	Iris-versicolor
    6.1	3.0	4.6	1.4	Iris-versicolor
    5.8	2.6	4.0	1.2	Iris-versicolor
    5.0	2.3	3.3	1.0	Iris-versicolor
    5.6	2.7	4.2	1.3	Iris-versicolor
    5.7	3.0	4.2	1.2	Iris-versicolor
    5.7	2.9	4.2	1.3	Iris-versicolor
    6.2	2.9	4.3	1.3	Iris-versicolor
    5.1	2.5	3.0	1.1	Iris-versicolor
    5.7	2.8	4.1	1.3	Iris-versicolor
    6.3	3.3	6.0	2.5	Iris-virginica
    5.8	2.7	5.1	1.9	Iris-virginica
    7.1	3.0	5.9	2.1	Iris-virginica
    6.3	2.9	5.6	1.8	Iris-virginica
    6.5	3.0	5.8	2.2	Iris-virginica
    7.6	3.0	6.6	2.1	Iris-virginica
    4.9	2.5	4.5	1.7	Iris-virginica
    7.3	2.9	6.3	1.8	Iris-virginica
    6.7	2.5	5.8	1.8	Iris-virginica
    7.2	3.6	6.1	2.5	Iris-virginica
    6.5	3.2	5.1	2.0	Iris-virginica
    6.4	2.7	5.3	1.9	Iris-virginica
    6.8	3.0	5.5	2.1	Iris-virginica
    5.7	2.5	5.0	2.0	Iris-virginica
    5.8	2.8	5.1	2.4	Iris-virginica
    6.4	3.2	5.3	2.3	Iris-virginica
    6.5	3.0	5.5	1.8	Iris-virginica
    7.7	3.8	6.7	2.2	Iris-virginica
    7.7	2.6	6.9	2.3	Iris-virginica
    6.0	2.2	5.0	1.5	Iris-virginica
    6.9	3.2	5.7	2.3	Iris-virginica
    5.6	2.8	4.9	2.0	Iris-virginica
    7.7	2.8	6.7	2.0	Iris-virginica
    6.3	2.7	4.9	1.8	Iris-virginica
    6.7	3.3	5.7	2.1	Iris-virginica
    7.2	3.2	6.0	1.8	Iris-virginica
    6.2	2.8	4.8	1.8	Iris-virginica
    6.1	3.0	4.9	1.8	Iris-virginica
    6.4	2.8	5.6	2.1	Iris-virginica
    7.2	3.0	5.8	1.6	Iris-virginica
    7.4	2.8	6.1	1.9	Iris-virginica
    7.9	3.8	6.4	2.0	Iris-virginica
    6.4	2.8	5.6	2.2	Iris-virginica
    6.3	2.8	5.1	1.5	Iris-virginica
    6.1	2.6	5.6	1.4	Iris-virginica
    7.7	3.0	6.1	2.3	Iris-virginica
    6.3	3.4	5.6	2.4	Iris-virginica
    6.4	3.1	5.5	1.8	Iris-virginica
    6.0	3.0	4.8	1.8	Iris-virginica
    6.9	3.1	5.4	2.1	Iris-virginica
    6.7	3.1	5.6	2.4	Iris-virginica
    6.9	3.1	5.1	2.3	Iris-virginica
    5.8	2.7	5.1	1.9	Iris-virginica
    6.8	3.2	5.9	2.3	Iris-virginica
    6.7	3.3	5.7	2.5	Iris-virginica
    6.7	3.0	5.2	2.3	Iris-virginica
    6.3	2.5	5.0	1.9	Iris-virginica
    6.5	3.0	5.2	2.0	Iris-virginica
    6.2	3.4	5.4	2.3	Iris-virginica
    5.9	3.0	5.1	1.8	Iris-virginica
    ```
    > Your command :
    ```
    sed -i 's/,/\t/g' iris.data
    ```
1. In the file ``/home/student/iris.data``, extract from this file the column 3 (petal length in cm) (use cut )
    > Your response :  
    ```
    1.4
    1.4
    1.3
    1.5
    1.4
    1.7
    1.4
    1.5
    1.4
    1.5
    1.5
    1.6
    1.4
    1.1
    1.2
    1.5
    1.3
    1.4
    1.7
    1.5
    1.7
    1.5
    1.0
    1.7
    1.9
    1.6
    1.6
    1.5
    1.4
    1.6
    1.6
    1.5
    1.5
    1.4
    1.5
    1.2
    1.3
    1.5
    1.3
    1.5
    1.3
    1.3
    1.3
    1.6
    1.9
    1.4
    1.6
    1.4
    1.5
    1.4
    4.7
    4.5
    4.9
    4.0
    4.6
    4.5
    4.7
    3.3
    4.6
    3.9
    3.5
    4.2
    4.0
    4.7
    3.6
    4.4
    4.5
    4.1
    4.5
    3.9
    4.8
    4.0
    4.9
    4.7
    4.3
    4.4
    4.8
    5.0
    4.5
    3.5
    3.8
    3.7
    3.9
    5.1
    4.5
    4.5
    4.7
    4.4
    4.1
    4.0
    4.4
    4.6
    4.0
    3.3
    4.2
    4.2
    4.2
    4.3
    3.0
    4.1
    4.7
    4.5
    4.9
    4.0
    4.6
    4.5
    4.7
    3.3
    4.6
    3.9
    3.5
    4.2
    4.0
    4.7
    3.6
    4.4
    4.5
    4.1
    4.5
    3.9
    4.8
    4.0
    4.9
    4.7
    4.3
    4.4
    4.8
    5.0
    4.5
    3.5
    3.8
    3.7
    3.9
    5.1
    4.5
    4.5
    4.7
    4.4
    4.1
    4.0
    4.4
    4.6
    4.0
    3.3
    4.2
    4.2
    4.2
    4.3
    3.0
    4.1
    6.0
    5.1
    5.9
    5.6
    5.8
    6.6
    4.5
    6.3
    5.8
    6.1
    5.1
    5.3
    5.5
    5.0
    5.1
    5.3
    5.5
    6.7
    6.9
    5.0
    5.7
    4.9
    6.7
    4.9
    5.7
    6.0
    4.8
    4.9
    5.6
    5.8
    6.1
    6.4
    5.6
    5.1
    5.6
    6.1
    5.6
    5.5
    4.8
    5.4
    5.6
    5.1
    5.1
    5.9
    5.7
    5.2
    5.0
    5.2
    5.4
    5.1
    ```
    > Your command :
    ```
    cut -d $'\t' -f 3 iris.data
    ```
1. In the file ``/home/student/iris.data``, count the number of flower species (cut and uniq)
    > Your response :  
    ```
    Iris-setosa
    Iris-versicolor
    Iris-virginica
    ```
    > Your command :
    ```
    cut -d $'\t' -f 5 iris.data | uniq
    ```
1. In the file ``/home/student/iris.data``, sort by increasing petal length (see sort options)
    > Your response :  
    ```
    4.6	3.6	1.0	0.2	Iris-setosa
    4.3	3.0	1.1	0.1	Iris-setosa
    5.0	3.2	1.2	0.2	Iris-setosa
    5.8	4.0	1.2	0.2	Iris-setosa
    4.4	3.0	1.3	0.2	Iris-setosa
    4.4	3.2	1.3	0.2	Iris-setosa
    4.7	3.2	1.3	0.2	Iris-setosa
    5.5	3.5	1.3	0.2	Iris-setosa
    4.5	2.3	1.3	0.3	Iris-setosa
    5.0	3.5	1.3	0.3	Iris-setosa
    5.4	3.9	1.3	0.4	Iris-setosa
    4.8	3.0	1.4	0.1	Iris-setosa
    4.4	2.9	1.4	0.2	Iris-setosa
    4.6	3.2	1.4	0.2	Iris-setosa
    4.9	3.0	1.4	0.2	Iris-setosa
    5.0	3.3	1.4	0.2	Iris-setosa
    5.0	3.6	1.4	0.2	Iris-setosa
    5.1	3.5	1.4	0.2	Iris-setosa
    5.2	3.4	1.4	0.2	Iris-setosa
    5.5	4.2	1.4	0.2	Iris-setosa
    4.6	3.4	1.4	0.3	Iris-setosa
    4.8	3.0	1.4	0.3	Iris-setosa
    5.1	3.5	1.4	0.3	Iris-setosa
    4.9	3.1	1.5	0.1	Iris-setosa
    4.9	3.1	1.5	0.1	Iris-setosa
    4.9	3.1	1.5	0.1	Iris-setosa
    5.2	4.1	1.5	0.1	Iris-setosa
    4.6	3.1	1.5	0.2	Iris-setosa
    5.0	3.4	1.5	0.2	Iris-setosa
    5.1	3.4	1.5	0.2	Iris-setosa
    5.2	3.5	1.5	0.2	Iris-setosa
    5.3	3.7	1.5	0.2	Iris-setosa
    5.4	3.7	1.5	0.2	Iris-setosa
    5.1	3.8	1.5	0.3	Iris-setosa
    5.1	3.7	1.5	0.4	Iris-setosa
    5.4	3.4	1.5	0.4	Iris-setosa
    5.7	4.4	1.5	0.4	Iris-setosa
    4.7	3.2	1.6	0.2	Iris-setosa
    4.8	3.1	1.6	0.2	Iris-setosa
    4.8	3.4	1.6	0.2	Iris-setosa
    5.0	3.0	1.6	0.2	Iris-setosa
    5.1	3.8	1.6	0.2	Iris-setosa
    5.0	3.4	1.6	0.4	Iris-setosa
    5.0	3.5	1.6	0.6	Iris-setosa
    5.4	3.4	1.7	0.2	Iris-setosa
    5.7	3.8	1.7	0.3	Iris-setosa
    5.4	3.9	1.7	0.4	Iris-setosa
    5.1	3.3	1.7	0.5	Iris-setosa
    4.8	3.4	1.9	0.2	Iris-setosa
    5.1	3.8	1.9	0.4	Iris-setosa
    5.1	2.5	3.0	1.1	Iris-versicolor
    5.1	2.5	3.0	1.1	Iris-versicolor
    4.9	2.4	3.3	1.0	Iris-versicolor
    4.9	2.4	3.3	1.0	Iris-versicolor
    5.0	2.3	3.3	1.0	Iris-versicolor
    5.0	2.3	3.3	1.0	Iris-versicolor
    5.0	2.0	3.5	1.0	Iris-versicolor
    5.0	2.0	3.5	1.0	Iris-versicolor
    5.7	2.6	3.5	1.0	Iris-versicolor
    5.7	2.6	3.5	1.0	Iris-versicolor
    5.6	2.9	3.6	1.3	Iris-versicolor
    5.6	2.9	3.6	1.3	Iris-versicolor
    5.5	2.4	3.7	1.0	Iris-versicolor
    5.5	2.4	3.7	1.0	Iris-versicolor
    5.5	2.4	3.8	1.1	Iris-versicolor
    5.5	2.4	3.8	1.1	Iris-versicolor
    5.6	2.5	3.9	1.1	Iris-versicolor
    5.6	2.5	3.9	1.1	Iris-versicolor
    5.8	2.7	3.9	1.2	Iris-versicolor
    5.8	2.7	3.9	1.2	Iris-versicolor
    5.2	2.7	3.9	1.4	Iris-versicolor
    5.2	2.7	3.9	1.4	Iris-versicolor
    6.0	2.2	4.0	1.0	Iris-versicolor
    6.0	2.2	4.0	1.0	Iris-versicolor
    5.8	2.6	4.0	1.2	Iris-versicolor
    5.8	2.6	4.0	1.2	Iris-versicolor
    5.5	2.3	4.0	1.3	Iris-versicolor
    5.5	2.3	4.0	1.3	Iris-versicolor
    5.5	2.5	4.0	1.3	Iris-versicolor
    5.5	2.5	4.0	1.3	Iris-versicolor
    6.1	2.8	4.0	1.3	Iris-versicolor
    6.1	2.8	4.0	1.3	Iris-versicolor
    5.8	2.7	4.1	1.0	Iris-versicolor
    5.8	2.7	4.1	1.0	Iris-versicolor
    5.6	3.0	4.1	1.3	Iris-versicolor
    5.6	3.0	4.1	1.3	Iris-versicolor
    5.7	2.8	4.1	1.3	Iris-versicolor
    5.7	2.8	4.1	1.3	Iris-versicolor
    5.7	3.0	4.2	1.2	Iris-versicolor
    5.7	3.0	4.2	1.2	Iris-versicolor
    5.6	2.7	4.2	1.3	Iris-versicolor
    5.6	2.7	4.2	1.3	Iris-versicolor
    5.7	2.9	4.2	1.3	Iris-versicolor
    5.7	2.9	4.2	1.3	Iris-versicolor
    5.9	3.0	4.2	1.5	Iris-versicolor
    5.9	3.0	4.2	1.5	Iris-versicolor
    6.2	2.9	4.3	1.3	Iris-versicolor
    6.2	2.9	4.3	1.3	Iris-versicolor
    6.4	2.9	4.3	1.3	Iris-versicolor
    6.4	2.9	4.3	1.3	Iris-versicolor
    5.5	2.6	4.4	1.2	Iris-versicolor
    5.5	2.6	4.4	1.2	Iris-versicolor
    6.3	2.3	4.4	1.3	Iris-versicolor
    6.3	2.3	4.4	1.3	Iris-versicolor
    6.6	3.0	4.4	1.4	Iris-versicolor
    6.6	3.0	4.4	1.4	Iris-versicolor
    6.7	3.1	4.4	1.4	Iris-versicolor
    6.7	3.1	4.4	1.4	Iris-versicolor
    5.7	2.8	4.5	1.3	Iris-versicolor
    5.7	2.8	4.5	1.3	Iris-versicolor
    5.4	3.0	4.5	1.5	Iris-versicolor
    5.4	3.0	4.5	1.5	Iris-versicolor
    5.6	3.0	4.5	1.5	Iris-versicolor
    5.6	3.0	4.5	1.5	Iris-versicolor
    6.0	2.9	4.5	1.5	Iris-versicolor
    6.0	2.9	4.5	1.5	Iris-versicolor
    6.2	2.2	4.5	1.5	Iris-versicolor
    6.2	2.2	4.5	1.5	Iris-versicolor
    6.4	3.2	4.5	1.5	Iris-versicolor
    6.4	3.2	4.5	1.5	Iris-versicolor
    6.0	3.4	4.5	1.6	Iris-versicolor
    6.0	3.4	4.5	1.6	Iris-versicolor
    4.9	2.5	4.5	1.7	Iris-virginica
    6.6	2.9	4.6	1.3	Iris-versicolor
    6.6	2.9	4.6	1.3	Iris-versicolor
    6.1	3.0	4.6	1.4	Iris-versicolor
    6.1	3.0	4.6	1.4	Iris-versicolor
    6.5	2.8	4.6	1.5	Iris-versicolor
    6.5	2.8	4.6	1.5	Iris-versicolor
    6.1	2.8	4.7	1.2	Iris-versicolor
    6.1	2.8	4.7	1.2	Iris-versicolor
    6.1	2.9	4.7	1.4	Iris-versicolor
    6.1	2.9	4.7	1.4	Iris-versicolor
    7.0	3.2	4.7	1.4	Iris-versicolor
    7.0	3.2	4.7	1.4	Iris-versicolor
    6.7	3.1	4.7	1.5	Iris-versicolor
    6.7	3.1	4.7	1.5	Iris-versicolor
    6.3	3.3	4.7	1.6	Iris-versicolor
    6.3	3.3	4.7	1.6	Iris-versicolor
    6.8	2.8	4.8	1.4	Iris-versicolor
    6.8	2.8	4.8	1.4	Iris-versicolor
    5.9	3.2	4.8	1.8	Iris-versicolor
    5.9	3.2	4.8	1.8	Iris-versicolor
    6.0	3.0	4.8	1.8	Iris-virginica
    6.2	2.8	4.8	1.8	Iris-virginica
    6.3	2.5	4.9	1.5	Iris-versicolor
    6.3	2.5	4.9	1.5	Iris-versicolor
    6.9	3.1	4.9	1.5	Iris-versicolor
    6.9	3.1	4.9	1.5	Iris-versicolor
    6.1	3.0	4.9	1.8	Iris-virginica
    6.3	2.7	4.9	1.8	Iris-virginica
    5.6	2.8	4.9	2.0	Iris-virginica
    6.0	2.2	5.0	1.5	Iris-virginica
    6.7	3.0	5.0	1.7	Iris-versicolor
    6.7	3.0	5.0	1.7	Iris-versicolor
    6.3	2.5	5.0	1.9	Iris-virginica
    5.7	2.5	5.0	2.0	Iris-virginica
    6.3	2.8	5.1	1.5	Iris-virginica
    6.0	2.7	5.1	1.6	Iris-versicolor
    6.0	2.7	5.1	1.6	Iris-versicolor
    5.9	3.0	5.1	1.8	Iris-virginica
    5.8	2.7	5.1	1.9	Iris-virginica
    5.8	2.7	5.1	1.9	Iris-virginica
    6.5	3.2	5.1	2.0	Iris-virginica
    6.9	3.1	5.1	2.3	Iris-virginica
    5.8	2.8	5.1	2.4	Iris-virginica
    6.5	3.0	5.2	2.0	Iris-virginica
    6.7	3.0	5.2	2.3	Iris-virginica
    6.4	2.7	5.3	1.9	Iris-virginica
    6.4	3.2	5.3	2.3	Iris-virginica
    6.9	3.1	5.4	2.1	Iris-virginica
    6.2	3.4	5.4	2.3	Iris-virginica
    6.4	3.1	5.5	1.8	Iris-virginica
    6.5	3.0	5.5	1.8	Iris-virginica
    6.8	3.0	5.5	2.1	Iris-virginica
    6.1	2.6	5.6	1.4	Iris-virginica
    6.3	2.9	5.6	1.8	Iris-virginica
    6.4	2.8	5.6	2.1	Iris-virginica
    6.4	2.8	5.6	2.2	Iris-virginica
    6.3	3.4	5.6	2.4	Iris-virginica
    6.7	3.1	5.6	2.4	Iris-virginica
    6.7	3.3	5.7	2.1	Iris-virginica
    6.9	3.2	5.7	2.3	Iris-virginica
    6.7	3.3	5.7	2.5	Iris-virginica
    7.2	3.0	5.8	1.6	Iris-virginica
    6.7	2.5	5.8	1.8	Iris-virginica
    6.5	3.0	5.8	2.2	Iris-virginica
    7.1	3.0	5.9	2.1	Iris-virginica
    6.8	3.2	5.9	2.3	Iris-virginica
    7.2	3.2	6.0	1.8	Iris-virginica
    6.3	3.3	6.0	2.5	Iris-virginica
    7.4	2.8	6.1	1.9	Iris-virginica
    7.7	3.0	6.1	2.3	Iris-virginica
    7.2	3.6	6.1	2.5	Iris-virginica
    7.3	2.9	6.3	1.8	Iris-virginica
    7.9	3.8	6.4	2.0	Iris-virginica
    7.6	3.0	6.6	2.1	Iris-virginica
    7.7	2.8	6.7	2.0	Iris-virginica
    7.7	3.8	6.7	2.2	Iris-virginica
    7.7	2.6	6.9	2.3	Iris-virginica
    ```
    > Your command :
    ```
    sort -k 3 iris.data
    ```
1. In the file ``/home/student/iris.data``, show only lines with petal length greater than the average size
    > Your response :  
    > Your command :
1. Using ``/etc/passwd``, extract the user and home directory fields for all users on your student
machine for which the shell is set to ``/bin/false``. 
    > Your response :
    ```
    systemd-timesync	/run/systemd
    systemd-network	/run/systemd/netif
    systemd-resolve	/run/systemd/resolve
    systemd-bus-proxy	/run/systemd
    syslog	/home/syslog
    _apt	/nonexistent
    lxd	/var/lib/lxd/
    mysql	/nonexistent
    messagebus	/var/run/dbus
    uuidd	/run/uuidd
    dnsmasq	/var/lib/misc
    postfix	/var/spool/postfix
    dovecot	/usr/lib/dovecot
    dovenull	/nonexistent
    colord	/var/lib/colord
    ```
    > Your command
    ```
    grep "/bin/false$" /etc/passwd | awk -F ':' '{print $1 "\t" $6}'
    ```

