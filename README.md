# InterviewExperienceAndDSAQuestions_lokesh

#payu

round1: 
- https://leetcode.com/problems/max-consecutive-ones-iii/description/
- https://www.geeksforgeeks.org/find-the-nearest-smaller-numbers-on-left-side-in-an-array/
- work exp

round2:
- java/springboot questions
	- Explain system.out.println()
	- Questions around different annotations in springboot
- sql (self-join)
- work exp
- LLD of Fitness App (Rewards/Goals,Notification,Analytics)

round3:
- https://www.geeksforgeeks.org/maximum-sum-path-across-two-arrays/
- work exp
- behavoiral questions

  First round -- 
1. HashMap related question  frequency, and indexes kaa use karna tha  , logic pucha tha bas exact yaad nahi kya question tha 
2. SQL ( employee aur salary table hai har employee ke corresponding salary batani hai 
3. MultiThreading 
4. Deadlock kaa code likhwaya 
     
Round 2 : core Java , collection frame work , 2 java object hai unke  distinct parameters ko ek set mei chahiye, hashcode aur equals method se related tha, 
Jdbc 
Springboot 


Round 3 : high level design related to microservice, 
Transaction management, concurrency management, hashing 

Round 4 : general discussion 

## SOme DSA INterview Questions:
Q-1: We are given 2D array and we need to complete the GetFInalImagefunction()
WHich takes input as rotation, vertical_flip and horizontal_flip
We need to return final 2D array by applying all this operations.
SOlution: 
Eg: n = 3, rotation 270, vertical_flip = 0, horizontal_flip = 1
input array: [1,0,0]
             [0,1,1]
             [0,0,1]
Code: 
Matrix processImage(Matrix &mat, int rotation, int vertical_flip, int horizontal_flip) {
    // Apply rotation
    if (rotation == 90) {
        mat = rotate90(mat);
    } else if (rotation == 180) {
        mat = rotate180(mat);
    } else if (rotation == 270) {
        mat = rotate270(mat);
    }

    // Apply vertical flip if necessar
    if (vertical_flip == 1) {
        mat = flipVertical(mat);
    }

    // Apply horizontal flip if necessary
    if (horizontal_flip == 1) {
        mat = flipHorizontal(mat);
    }

    return mat;
}
Matrix rotate90(Matrix &mat) {
    int n = mat.size();
    Matrix rotated(n, vector<int>(n));
    for (int i = 0; i < n; i++) {
        for (int j = 0; j < n; j++) {
            rotated[j][n - i - 1] = mat[i][j];
        }
    }
    return rotated;
}

// Function to rotate the matrix by 180 degrees
Matrix rotate180(Matrix &mat) {
    return rotate90(rotate90(mat));
}

// Function to rotate the matrix by 270 degrees
Matrix rotate270(Matrix &mat) {
    return rotate90(rotate180(mat));
}

// Function to vertically flip the matrix
Matrix flipVertical(Matrix &mat) {
    int n = mat.size();
    for (int i = 0; i < n / 2; i++) {
        swap(mat[i], mat[n - i - 1]);
    }
    return mat;
}

// Function to horizontally flip the matrix
Matrix flipHorizontal(Matrix &mat) {
    int n = mat.size();
    for (int i = 0; i < n; i++) {
        reverse(mat[i].begin(), mat[i].end());
    }
    return mat;
}

// Function to process the image
Matrix processImage(Matrix &mat, int rotation, int vertical_flip, int horizontal_flip) {
    // Apply rotation
    if (rotation == 90) {
        mat = rotate90(mat);
    } else if (rotation == 180) {
        mat = rotate180(mat);
    } else if (rotation == 270) {
        mat = rotate270(mat);
    }

    // Apply vertical flip if necessary
    if (vertical_flip == 1) {
        mat = flipVertical(mat);
    }

    // Apply horizontal flip if necessary
    if (horizontal_flip == 1) {
        mat = flipHorizontal(mat);
    }

    return mat;
}

Q-2: we have given two tables customers and wareHouses
customerSchema: id, name
wareHouseSchema: cust_id,volumen,is_Active
Result should have following column
customer_name, warehouses(total_num of ActiveWareHouse), min_volumne,max_volumen(largest active warehouse), total_volume(shows all active warehouses)

Select c.customer_name, count(w.c_id), min(w.volumen), max(w.volumen), sum(w.volume) from customers as c
Join warehouses w on c.id == w.c_id where w.isActive = true group by c.name ASC;






Majorily yahi yaad hai yaar
