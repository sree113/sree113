
public class Strmnp {
    public int minDistance(String w1, String w2) {
        int[][] d=new int[w1.length()+1][w2.length()+1];
        d[0][0]=0;
        for(int i=1;i<=w1.length();i++) d[i][0]=i;
        for(int j=1;j<=w2.length();j++) d[0][j]=j;
        for(int i=1;i<=w1.length();i++){
            for(int j=1;j<=w2.length();j++){
                if(w1.charAt(i-1)==w2.charAt(j-1)) d[i][j]=d[i-1][j-1];
                else d[i][j]=Math.min(Math.min(d[i-1][j],d[i][j-1]),d[i-1][j-1])+1;
            }
        }
        return d[w1.length()][w2.length()];
    }
}
