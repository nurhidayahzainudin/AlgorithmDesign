# AlgorithmDesign

package lab6q1;

public class Lab6Q1 {
    static int HeapSize;
static int[]A = {11,4,74,55,3,17,8,46,43,33};

    public static void main(String[] args) {
        buildMaxHeap(A);

        for(int k = 0; k<A.length; k++){
            System.out.println(A[k]);
        }
    }
    
    //Buat Max Heap
    public static void buildMaxHeap(int[]A){
        HeapSize = A.length-1;
        //start dari parent paling belakang (HeapSize/2)
        for(int i = HeapSize/2; i>=0 ; i--)
        MaxHeapify(A,i);
    }
    
    //Make sure its always Max Heap
    public static void MaxHeapify(int[]A, int i){
        int l = Left(i);
        int r = Right(i);
        int largest=i;
        
        if(l<=HeapSize && A[l]>A[i])
            largest = l;
        
        if(r<=HeapSize && A[r]>A[largest])
            largest=r;
        
        if (largest!=i){
            int temp = A[i];
            A[i]=A[largest];
            A[largest]=temp;
            MaxHeapify(A,largest);
        }
    }
   
    // Return left child
    public static int Left(int i){
        return 2*i;
    } 
    
    // Return right child
    public static int Right(int i){
        return 2*i+1;
    }
}
