
Section 1: Exploratory Data Analysis (10 questions)
#Load the dataset smartphones.csv using pandas
import pandas as pd
# Load the dataset
df = pd.read_csv(r"C:\Users\savai\Documents\Documents\Smartphones_cleaned_dataset.csv")
# Display the first few rows of the dataset
print(df.head())
  brand_name                      model  price  rating  has_5g  has_nfc  \
0    oneplus              OnePlus 11 5G  54999    89.0    True     True   
1    oneplus  OnePlus Nord CE 2 Lite 5G  19989    81.0    True    False   
2    samsung      Samsung Galaxy A14 5G  16499    75.0    True    False   
3   motorola       Motorola Moto G62 5G  14999    81.0    True    False   
4     realme         Realme 10 Pro Plus  24999    82.0    True    False   

   has_ir_blaster processor_brand  num_cores  processor_speed  ...  \
0           False      snapdragon        8.0              3.2  ...   
1           False      snapdragon        8.0              2.2  ...   
2           False          exynos        8.0              2.4  ...   
3           False      snapdragon        8.0              2.2  ...   
4           False       dimensity        8.0              2.6  ...   

   refresh_rate  num_rear_cameras  num_front_cameras       os  \
0           120                 3                1.0  android   
1           120                 3                1.0  android   
2            90                 3                1.0  android   
3           120                 3                1.0  android   
4           120                 3                1.0  android   

   primary_camera_rear  primary_camera_front  extended_memory_available  \
0                 50.0                  16.0                          0   
1                 64.0                  16.0                          1   
2                 50.0                  13.0                          1   
3                 50.0                  16.0                          1   
4                108.0                  16.0                          0   

   extended_upto  resolution_width resolution_height  
0            NaN              1440              3216  
1         1024.0              1080              2412  
2         1024.0              1080              2408  
3         1024.0              1080              2400  
4            NaN              1080              2412  

[5 rows x 26 columns]
#Q2. Display the shape of the dataset.
# Display the shape of the dataset
print("Shape of the dataset:", df.shape)
Shape of the dataset: (980, 26)
#print the first 10 rows of the dataset
print(df.head(10))
  brand_name                                    model  price  rating  has_5g  \
0    oneplus                            OnePlus 11 5G  54999    89.0    True   
1    oneplus                OnePlus Nord CE 2 Lite 5G  19989    81.0    True   
2    samsung                    Samsung Galaxy A14 5G  16499    75.0    True   
3   motorola                     Motorola Moto G62 5G  14999    81.0    True   
4     realme                       Realme 10 Pro Plus  24999    82.0    True   
5    samsung  Samsung Galaxy F23 5G (6GB RAM + 128GB)  16999    80.0    True   
6      apple                          Apple iPhone 14  65999    81.0    True   
7     xiaomi            Xiaomi Redmi Note 12 Pro Plus  29999    86.0    True   
8    nothing                          Nothing Phone 1  26749    85.0    True   
9    oneplus                       OnePlus Nord 2T 5G  28999    84.0    True   

   has_nfc  has_ir_blaster processor_brand  num_cores  processor_speed  ...  \
0     True           False      snapdragon        8.0             3.20  ...   
1    False           False      snapdragon        8.0             2.20  ...   
2    False           False          exynos        8.0             2.40  ...   
3    False           False      snapdragon        8.0             2.20  ...   
4    False           False       dimensity        8.0             2.60  ...   
5     True           False      snapdragon        8.0             2.20  ...   
6     True           False          bionic        6.0             3.22  ...   
7    False            True       dimensity        8.0             2.60  ...   
8     True           False      snapdragon        8.0             2.50  ...   
9     True           False       dimensity        8.0             3.00  ...   

   refresh_rate  num_rear_cameras  num_front_cameras       os  \
0           120                 3                1.0  android   
1           120                 3                1.0  android   
2            90                 3                1.0  android   
3           120                 3                1.0  android   
4           120                 3                1.0  android   
5           120                 3                1.0  android   
6            60                 2                1.0      ios   
7           120                 3                1.0  android   
8           120                 2                1.0  android   
9            90                 3                1.0  android   

   primary_camera_rear  primary_camera_front  extended_memory_available  \
0                 50.0                  16.0                          0   
1                 64.0                  16.0                          1   
2                 50.0                  13.0                          1   
3                 50.0                  16.0                          1   
4                108.0                  16.0                          0   
5                 50.0                   8.0                          1   
6                 12.0                  12.0                          0   
7                200.0                  16.0                          0   
8                 50.0                  16.0                          0   
9                 50.0                  32.0                          0   

   extended_upto  resolution_width resolution_height  
0            NaN              1440              3216  
1         1024.0              1080              2412  
2         1024.0              1080              2408  
3         1024.0              1080              2400  
4            NaN              1080              2412  
5         1024.0              1080              2408  
6            NaN              1170              2532  
7            NaN              1080              2400  
8            NaN              1080              2400  
9            NaN              1080              2400  

[10 rows x 26 columns]
#Q4. Find all rows where the price is more than 30,000.
# Find all rows where the price is more than 30,000
high_price_df = df[df['price'] > 30000]
# Display the rows with price more than 30,000
print("Rows where price is more than 30,000:")
print(high_price_df)
Rows where price is more than 30,000:
    brand_name                        model   price  rating  has_5g  has_nfc  \
0      oneplus                OnePlus 11 5G   54999    89.0    True     True   
6        apple              Apple iPhone 14   65999    81.0    True     True   
14     samsung  Samsung Galaxy S23 Ultra 5G  114990     NaN    True     True   
15       apple              Apple iPhone 13   62999    79.0    True     True   
17        oppo         OPPO Reno 9 Pro Plus   45999    86.0    True     True   
..         ...                          ...     ...     ...     ...      ...   
969     xiaomi                Xiaomi Civi 3   32990    86.0    True     True   
971       oppo                 Oppo Find X6   69990    89.0    True     True   
973     google           Google Pixel 8 Pro   70990    80.0    True     True   
974       vivo                Vivo X Fold 2  119990     NaN    True     True   
975   motorola   Motorola Moto Edge S30 Pro   34990    83.0    True    False   

     has_ir_blaster processor_brand  num_cores  processor_speed  ...  \
0             False      snapdragon        8.0             3.20  ...   
6             False          bionic        6.0             3.22  ...   
14            False      snapdragon        8.0             3.20  ...   
15            False          bionic        6.0             3.22  ...   
17            False      snapdragon        8.0             3.20  ...   
..              ...             ...        ...              ...  ...   
969            True       dimensity        8.0             3.10  ...   
971           False      snapdragon        8.0             3.20  ...   
973           False          google        8.0              NaN  ...   
974           False      snapdragon        8.0             3.20  ...   
975           False      snapdragon        8.0             3.00  ...   

     refresh_rate  num_rear_cameras  num_front_cameras       os  \
0             120                 3                1.0  android   
6              60                 2                1.0      ios   
14            120                 4                1.0  android   
15             60                 2                1.0      ios   
17            120                 3                1.0  android   
..            ...               ...                ...      ...   
969           120                 3                2.0  android   
971           120                 3                1.0  android   
973           120                 3                1.0  android   
974           120                 3                1.0  android   
975           120                 3                1.0  android   

     primary_camera_rear  primary_camera_front  extended_memory_available  \
0                   50.0                  16.0                          0   
6                   12.0                  12.0                          0   
14                 200.0                  12.0                          0   
15                  12.0                  12.0                          0   
17                  50.0                  32.0                          0   
..                   ...                   ...                        ...   
969                 64.0                  32.0                          0   
971                 50.0                  32.0                          0   
973                 50.0                  12.0                          0   
974                 50.0                  32.0                          0   
975                 64.0                  16.0                          0   

     extended_upto  resolution_width resolution_height  
0              NaN              1440              3216  
6              NaN              1170              2532  
14             NaN              1440              3088  
15             NaN              1170              2532  
17             NaN              1080              2412  
..             ...               ...               ...  
969            NaN              1080              2400  
971            NaN              1080              2400  
973            NaN              1440              3120  
974            NaN              1916              2160  
975            NaN              1080              2460  

[294 rows x 26 columns]
#Q5. Show all unique values in the brand_name column
# Show all unique values in the brand_name column
unique_brands = df['brand_name'].unique()
# Display the unique brands
print("Unique brands in the dataset:")
print(unique_brands)
Unique brands in the dataset:
['oneplus' 'samsung' 'motorola' 'realme' 'apple' 'xiaomi' 'nothing' 'oppo'
 'vivo' 'poco' 'iqoo' 'jio' 'gionee' 'tecno' 'tesla' 'google' 'infinix'
 'cola' 'letv' 'ikall' 'leeco' 'duoqin' 'nokia' 'lava' 'honor' 'nubia'
 'redmi' 'asus' 'itel' 'royole' 'sony' 'oukitel' 'vertu' 'blu' 'lyf'
 'huawei' 'zte' 'lenovo' 'lg' 'micromax' 'leitz' 'cat' 'doogee' 'tcl'
 'sharp' 'blackview']
#Q6. Check for missing values in the dataset.
# Check for missing values in the dataset
missing_values = df.isnull().sum()
# Display the count of missing values in each column
print("Missing values in each column:")
print(missing_values)
Missing values in each column:
brand_name                     0
model                          0
price                          0
rating                       101
has_5g                         0
has_nfc                        0
has_ir_blaster                 0
processor_brand               20
num_cores                      6
processor_speed               42
battery_capacity              11
fast_charging_available        0
fast_charging                211
ram_capacity                   0
internal_memory                0
screen_size                    0
refresh_rate                   0
num_rear_cameras               0
num_front_cameras              4
os                            14
primary_camera_rear            0
primary_camera_front           5
extended_memory_available      0
extended_upto                480
resolution_width               0
resolution_height              0
dtype: int64
#Q7. Find the average RAM of all smartphones.
# Find the average RAM of all smartphones
average_ram = df['ram_capacity'].mean()
# Display the average RAM
print("Average RAM of all smartphones:", average_ram)
Average RAM of all smartphones: 6.560204081632653
#Q8. Count the number of phones per brand.
# Count the number of phones per brand
phones_per_brand = df['brand_name'].value_counts()
# Display the count of phones per brand
print("Number of phones per brand:")
print(phones_per_brand)
Number of phones per brand:
brand_name
xiaomi       134
samsung      132
vivo         111
realme        97
oppo          88
motorola      52
apple         46
oneplus       42
poco          41
tecno         33
iqoo          32
infinix       29
huawei        16
google        14
nokia         13
honor         13
itel          10
sony           9
asus           7
nubia          6
nothing        5
jio            4
lava           4
gionee         3
letv           3
ikall          3
lg             3
oukitel        3
redmi          3
micromax       3
doogee         2
lenovo         2
zte            2
lyf            2
royole         2
tesla          1
leeco          1
duoqin         1
cola           1
blu            1
vertu          1
leitz          1
cat            1
tcl            1
sharp          1
blackview      1
Name: count, dtype: int64
#Q9. Show the summary statistics for numeric columns.
# Show the summary statistics for numeric columns
summary_statistics = df.describe()
# Display the summary statistics
print("Summary statistics for numeric columns:")
print(summary_statistics)
Summary statistics for numeric columns:
               price      rating   num_cores  processor_speed  \
count     980.000000  879.000000  974.000000       938.000000   
mean    32520.504082   78.258248    7.772074         2.427217   
std     39531.812669    7.402854    0.836845         0.464090   
min      3499.000000   60.000000    4.000000         1.200000   
25%     12999.000000   74.000000    8.000000         2.050000   
50%     19994.500000   80.000000    8.000000         2.300000   
75%     35491.500000   84.000000    8.000000         2.840000   
max    650000.000000   89.000000    8.000000         3.220000   

       battery_capacity  fast_charging_available  fast_charging  ram_capacity  \
count        969.000000               980.000000     769.000000    980.000000   
mean        4817.748194                 0.854082      46.126138      6.560204   
std         1009.540054                 0.353205      34.277870      2.744378   
min         1821.000000                 0.000000      10.000000      1.000000   
25%         4500.000000                 1.000000      18.000000      4.000000   
50%         5000.000000                 1.000000      33.000000      6.000000   
75%         5000.000000                 1.000000      66.000000      8.000000   
max        22000.000000                 1.000000     240.000000     18.000000   

       internal_memory  screen_size  refresh_rate  num_rear_cameras  \
count       980.000000   980.000000    980.000000        980.000000   
mean        141.036735     6.536765     92.256122          2.814286   
std         107.134516     0.349162     28.988052          0.776441   
min           8.000000     3.540000     60.000000          1.000000   
25%          64.000000     6.500000     60.000000          2.000000   
50%         128.000000     6.580000     90.000000          3.000000   
75%         128.000000     6.670000    120.000000          3.000000   
max        1024.000000     8.030000    240.000000          4.000000   

       num_front_cameras  primary_camera_rear  primary_camera_front  \
count         976.000000           980.000000            975.000000   
mean            1.029713            50.319286             16.589128   
std             0.169882            33.000968             10.876802   
min             1.000000             2.000000              0.300000   
25%             1.000000            24.000000              8.000000   
50%             1.000000            50.000000             16.000000   
75%             1.000000            64.000000             16.000000   
max             2.000000           200.000000             60.000000   

       extended_memory_available  extended_upto  resolution_width  \
count                 980.000000     500.000000        980.000000   
mean                    0.630612     736.064000       1075.852041   
std                     0.482885     366.894911        290.164931   
min                     0.000000      32.000000        480.000000   
25%                     0.000000     512.000000       1080.000000   
50%                     1.000000    1024.000000       1080.000000   
75%                     1.000000    1024.000000       1080.000000   
max                     1.000000    2048.000000       2460.000000   

       resolution_height  
count         980.000000  
mean         2214.663265  
std           516.484254  
min           480.000000  
25%          1612.000000  
50%          2400.000000  
75%          2408.000000  
max          3840.000000  
#Q10. Which line would show you correlation between numeric columns?
# Show the correlation between numeric columns
correlation_matrix = df.select_dtypes(include='number').corr()
# Display the correlation matrix
print("Correlation matrix between numeric columns:")
print(correlation_matrix)
Correlation matrix between numeric columns:
                              price    rating  num_cores  processor_speed  \
price                      1.000000  0.283504  -0.048561         0.474049   
rating                     0.283504  1.000000   0.199741         0.628446   
num_cores                 -0.048561  0.199741   1.000000         0.192863   
processor_speed            0.474049  0.628446   0.192863         1.000000   
battery_capacity          -0.159232 -0.015581   0.241289        -0.041930   
fast_charging_available    0.116739  0.542814   0.360476         0.345856   
fast_charging              0.277591  0.527613   0.115413         0.615657   
ram_capacity               0.386002  0.757613   0.303911         0.627234   
internal_memory            0.557168  0.481070   0.043934         0.525510   
screen_size                0.113253  0.298272   0.385652         0.290366   
refresh_rate               0.244115  0.610795   0.233010         0.555004   
num_rear_cameras           0.125330  0.515531   0.343150         0.255476   
num_front_cameras          0.115228  0.131480   0.047578         0.124191   
primary_camera_rear        0.092095  0.562046   0.312394         0.281204   
primary_camera_front       0.162995  0.577861   0.221483         0.398207   
extended_memory_available -0.448628 -0.415265   0.072934        -0.663085   
extended_upto              0.091945  0.346761   0.198742         0.259733   
resolution_width           0.340592  0.432582   0.137952         0.365757   
resolution_height          0.353578  0.688108   0.266491         0.553923   

                           battery_capacity  fast_charging_available  \
price                             -0.159232                 0.116739   
rating                            -0.015581                 0.542814   
num_cores                          0.241289                 0.360476   
processor_speed                   -0.041930                 0.345856   
battery_capacity                   1.000000                 0.128993   
fast_charging_available            0.128993                 1.000000   
fast_charging                     -0.078096                      NaN   
ram_capacity                       0.085690                 0.439538   
internal_memory                   -0.001444                 0.279877   
screen_size                        0.348805                 0.346687   
refresh_rate                       0.088636                 0.415278   
num_rear_cameras                   0.155410                 0.470952   
num_front_cameras                 -0.072366                 0.072208   
primary_camera_rear                0.171465                 0.427440   
primary_camera_front              -0.005111                 0.331769   
extended_memory_available          0.174683                -0.166626   
extended_upto                      0.238755                 0.333016   
resolution_width                  -0.024607                 0.318720   
resolution_height                  0.036503                 0.510112   

                           fast_charging  ram_capacity  internal_memory  \
price                           0.277591      0.386002         0.557168   
rating                          0.527613      0.757613         0.481070   
num_cores                       0.115413      0.303911         0.043934   
processor_speed                 0.615657      0.627234         0.525510   
battery_capacity               -0.078096      0.085690        -0.001444   
fast_charging_available              NaN      0.439538         0.279877   
fast_charging                   1.000000      0.533602         0.380985   
ram_capacity                    0.533602      1.000000         0.592332   
internal_memory                 0.380985      0.592332         1.000000   
screen_size                     0.258955      0.396613         0.276401   
refresh_rate                    0.546374      0.573977         0.380263   
num_rear_cameras                0.126803      0.384908         0.236609   
num_front_cameras               0.012674      0.167176         0.154839   
primary_camera_rear             0.390718      0.431377         0.200656   
primary_camera_front            0.392673      0.519891         0.256869   
extended_memory_available      -0.563131     -0.482666        -0.397903   
extended_upto                   0.026669      0.280564         0.232860   
resolution_width                0.222381      0.380274         0.341709   
resolution_height               0.331469      0.578105         0.427218   

                           screen_size  refresh_rate  num_rear_cameras  \
price                         0.113253      0.244115          0.125330   
rating                        0.298272      0.610795          0.515531   
num_cores                     0.385652      0.233010          0.343150   
processor_speed               0.290366      0.555004          0.255476   
battery_capacity              0.348805      0.088636          0.155410   
fast_charging_available       0.346687      0.415278          0.470952   
fast_charging                 0.258955      0.546374          0.126803   
ram_capacity                  0.396613      0.573977          0.384908   
internal_memory               0.276401      0.380263          0.236609   
screen_size                   1.000000      0.333411          0.371769   
refresh_rate                  0.333411      1.000000          0.293381   
num_rear_cameras              0.371769      0.293381          1.000000   
num_front_cameras             0.076910      0.015942          0.127444   
primary_camera_rear           0.329288      0.468284          0.455010   
primary_camera_front          0.214725      0.401396          0.406660   
extended_memory_available    -0.094878     -0.445877         -0.055110   
extended_upto                 0.265277      0.303460          0.100238   
resolution_width              0.334099      0.294688          0.342834   
resolution_height             0.295926      0.481937          0.465547   

                           num_front_cameras  primary_camera_rear  \
price                               0.115228             0.092095   
rating                              0.131480             0.562046   
num_cores                           0.047578             0.312394   
processor_speed                     0.124191             0.281204   
battery_capacity                   -0.072366             0.171465   
fast_charging_available             0.072208             0.427440   
fast_charging                       0.012674             0.390718   
ram_capacity                        0.167176             0.431377   
internal_memory                     0.154839             0.200656   
screen_size                         0.076910             0.329288   
refresh_rate                        0.015942             0.468284   
num_rear_cameras                    0.127444             0.455010   
num_front_cameras                   1.000000             0.020675   
primary_camera_rear                 0.020675             1.000000   
primary_camera_front                0.210436             0.478361   
extended_memory_available          -0.117231            -0.136152   
extended_upto                      -0.132291             0.345230   
resolution_width                    0.105720             0.257728   
resolution_height                   0.064311             0.394871   

                           primary_camera_front  extended_memory_available  \
price                                  0.162995                  -0.448628   
rating                                 0.577861                  -0.415265   
num_cores                              0.221483                   0.072934   
processor_speed                        0.398207                  -0.663085   
battery_capacity                      -0.005111                   0.174683   
fast_charging_available                0.331769                  -0.166626   
fast_charging                          0.392673                  -0.563131   
ram_capacity                           0.519891                  -0.482666   
internal_memory                        0.256869                  -0.397903   
screen_size                            0.214725                  -0.094878   
refresh_rate                           0.401396                  -0.445877   
num_rear_cameras                       0.406660                  -0.055110   
num_front_cameras                      0.210436                  -0.117231   
primary_camera_rear                    0.478361                  -0.136152   
primary_camera_front                   1.000000                  -0.328649   
extended_memory_available             -0.328649                   1.000000   
extended_upto                          0.181252                        NaN   
resolution_width                       0.262210                  -0.249250   
resolution_height                      0.415998                  -0.353785   

                           extended_upto  resolution_width  resolution_height  
price                           0.091945          0.340592           0.353578  
rating                          0.346761          0.432582           0.688108  
num_cores                       0.198742          0.137952           0.266491  
processor_speed                 0.259733          0.365757           0.553923  
battery_capacity                0.238755         -0.024607           0.036503  
fast_charging_available         0.333016          0.318720           0.510112  
fast_charging                   0.026669          0.222381           0.331469  
ram_capacity                    0.280564          0.380274           0.578105  
internal_memory                 0.232860          0.341709           0.427218  
screen_size                     0.265277          0.334099           0.295926  
refresh_rate                    0.303460          0.294688           0.481937  
num_rear_cameras                0.100238          0.342834           0.465547  
num_front_cameras              -0.132291          0.105720           0.064311  
primary_camera_rear             0.345230          0.257728           0.394871  
primary_camera_front            0.181252          0.262210           0.415998  
extended_memory_available            NaN         -0.249250          -0.353785  
extended_upto                   1.000000          0.076826           0.291772  
resolution_width                0.076826          1.000000           0.265519  
resolution_height               0.291772          0.265519           1.000000  
SECTION 2: Visualization & Plotting (10 questions)
#Q11. Import the required visualization libraries.
import matplotlib.pyplot as plt
import seaborn as sns
#Q12. Plot a histogram of Price.
# Plot a histogram of Price
plt.figure(figsize=(10, 6))
plt.hist(df['price'], bins=30, color='blue', alpha=0.7)
plt.title('Histogram of Smartphone Prices')
plt.xlabel('Price')
plt.ylabel('Frequency')
plt.grid(axis='y', alpha=0.75)
plt.show()

#Q13. Create a bar plot showing average price per brand.
# Create a bar plot showing average price per brand
plt.figure(figsize=(12, 6))
average_price_per_brand = df.groupby('brand_name')['price'].mean().sort_values(ascending=False)
average_price_per_brand.plot(kind='bar', color='skyblue')
plt.title('Average Price per Brand')
plt.xlabel('Brand Name')
plt.ylabel('Average Price')
plt.xticks(rotation=45)
plt.grid(axis='y', alpha=0.75)
plt.show()

#Q14. Plot a heatmap of correlations.
# Plot a heatmap of correlations
plt.figure(figsize=(12, 8))
correlation_matrix = df.select_dtypes(include='number').corr()
sns.heatmap(correlation_matrix, annot=True, fmt='.2f', cmap='coolwarm', square=True)
plt.title('Heatmap of Correlations')
plt.show()

#Q15. Show the relationship between RAM and Price using a scatter plot.
# Show the relationship between RAM and Price using a scatter plot
plt.figure(figsize=(10, 6))
plt.scatter(df['ram_capacity'], df['price'], alpha=0.5, color='green')
plt.title('Relationship between RAM and Price')
plt.xlabel('RAM Capacity (MB)')
plt.ylabel('Price')
plt.grid()
plt.show()

#Q16. Create a boxplot to visualize Price distribution across brands.
# Create a boxplot to visualize Price distribution across brands
plt.figure(figsize=(12, 6))
sns.boxplot(x='brand_name', y='price', data=df)
plt.title('Price Distribution across Brands')
plt.xlabel('Brand Name')
plt.ylabel('Price')
plt.xticks(rotation=45)
plt.grid(axis='y', alpha=0.75)
plt.show()

#Q18. Plot a KDE (density plot) of prices.
# Plot a KDE (density plot) of prices
plt.figure(figsize=(10, 6))
sns.kdeplot(df['price'], shade=True, color='purple')
plt.title('KDE Plot of Smartphone Prices')
plt.xlabel('Price')
plt.ylabel('Density')
plt.grid()
plt.show()
C:\Users\savai\AppData\Local\Temp\ipykernel_20964\744673301.py:4: FutureWarning: 

`shade` is now deprecated in favor of `fill`; setting `fill=True`.
This will become an error in seaborn v0.14.0; please update your code.

  sns.kdeplot(df['price'], shade=True, color='purple')

#Q19. Rotate x-axis labels for readability.
# Rotate x-axis labels for readability
plt.figure(figsize=(12, 6))
sns.countplot(x='brand_name', data=df)
plt.title('Count of Smartphones per Brand')
plt.xlabel('Brand Name')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.grid(axis='y', alpha=0.75)
plt.show()

#Q20. Save a seaborn plot to a file.
# Save a seaborn plot to a file
plt.figure(figsize=(10, 6))
sns.countplot(x='brand_name', data=df)
plt.title('Count of Smartphones per Brand')
plt.xlabel('Brand Name')
plt.ylabel('Count')
plt.xticks(rotation=45)
plt.grid(axis='y', alpha=0.75)
plt.savefig('smartphones_count_per_brand.png', bbox_inches='tight')
plt.show()

SECTION 3: Regression & Price Prediction (10 questions)
#Q21. Import the required regression libraries.
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error, r2_score
# Q22. Define features X and target y.
# Define features X and target y
X = df[['ram_capacity', 'battery_capacity', 'internal_memory']]
y = df['price']
# Q23. Split data into training and testing sets.
# Split data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
#Q24. Train a linear regression model.
from sklearn.impute import SimpleImputer

# Impute missing values in X_train
imputer = SimpleImputer(strategy='mean')
X_train_imputed = imputer.fit_transform(X_train)

# Train a linear regression model
model = LinearRegression()
model.fit(X_train_imputed, y_train)
LinearRegression()
In a Jupyter environment, please rerun this cell to show the HTML representation or trust the notebook.
On GitHub, the HTML representation is unable to render, please try loading this page with nbviewer.org.
#Q25. Make predictions on the test set.
# Make predictions on the test set
X_test_imputed = imputer.transform(X_test)
y_pred = model.predict(X_test_imputed)
#Q26. Calculate Mean Squared Error (MSE).
# Calculate Mean Squared Error (MSE)
mse = mean_squared_error(y_test, y_pred)
# Display the Mean Squared Error
print("Mean Squared Error (MSE):", mse)
Mean Squared Error (MSE): 435927808.4036026
#Q27. Print R² score.
# Print R² score
r2 = r2_score(y_test, y_pred)
print("R² Score:", r2)
R² Score: 0.5448835371067082
#Q28. Add a new feature: Price_per_GB = Price / Storage.
# Add a new feature: Price_per_GB = Price / Storage
df['price_per_gb'] = df['price'] / df['internal_memory']
# Display the first few rows with the new feature
print("First few rows with the new feature 'price_per_gb':")
print(df[['brand_name', 'internal_memory', 'price', 'price_per_gb']].head())
First few rows with the new feature 'price_per_gb':
  brand_name  internal_memory  price  price_per_gb
0    oneplus              256  54999    214.839844
1    oneplus              128  19989    156.164062
2    samsung               64  16499    257.796875
3   motorola              128  14999    117.179688
4     realme              128  24999    195.304688
#Q29. Scale features using StandardScaler.
from sklearn.preprocessing import StandardScaler
# Scale features using StandardScaler
scaler = StandardScaler()
# Fit the scaler on the training data and transform both training and test data
X_train_scaled = scaler.fit_transform(X_train_imputed)
# Transform the test data
X_test_scaled = scaler.transform(X_test_imputed)
# Display the first few rows of the scaled training data
print("First few rows of the scaled training data:")
print(pd.DataFrame(X_train_scaled, columns=X.columns).head())
First few rows of the scaled training data:
   ram_capacity  battery_capacity  internal_memory
0      0.518564         -0.775585        -0.122761
1      1.965376         -0.030228         1.061792
2     -0.928248          0.156111        -0.122761
3     -0.204842          0.156111        -0.122761
4     -0.928248         -1.604795        -0.715038
#Q30. Try a Decision Tree Regressor.
from sklearn.tree import DecisionTreeRegressor
# Train a Decision Tree Regressor
dt_model = DecisionTreeRegressor(random_state=42)
dt_model.fit(X_train_scaled, y_train)
# Make predictions using the Decision Tree model
y_pred_dt = dt_model.predict(X_test_scaled)
# Calculate Mean Squared Error for Decision Tree model
mse_dt = mean_squared_error(y_test, y_pred_dt)
# Display the Mean Squared Error for Decision Tree model
print("Mean Squared Error (MSE) for Decision Tree model:", mse_dt)
#Q31. Compare the performance of Linear Regression and Decision Tree Regressor.
# Compare the performance of Linear Regression and Decision Tree Regressor
print("Linear Regression MSE:", mse)
print("Decision Tree Regressor MSE:", mse_dt)
Mean Squared Error (MSE) for Decision Tree model: 519879265.6454514
Linear Regression MSE: 435927808.4036026
Decision Tree Regressor MSE: 519879265.6454514
SECTION 4: Feature Importance & Trend Analysis (10 questions)
#Q31. Get feature importances from a trained decision tree.
# Get feature importances from a trained decision tree
feature_importances = dt_model.feature_importances_
# Display the feature importances
print("Feature importances from the Decision Tree model:")
for feature, importance in zip(X.columns, feature_importances):
    print(f"{feature}: {importance:.4f}")
    
Feature importances from the Decision Tree model:
ram_capacity: 0.0669
battery_capacity: 0.5944
internal_memory: 0.3387
#Q32. Plot feature importances.
# Plot feature importances
plt.figure(figsize=(10, 6))
plt.barh(X.columns, feature_importances, color='orange')
plt.title('Feature Importances from Decision Tree Regressor')
plt.xlabel('Importance')
plt.ylabel('Features')
plt.grid(axis='x', alpha=0.75)
plt.show()

#Q33. Select top 3 features using SelectKBest.
from sklearn.feature_selection import SelectKBest, f_regression
# Impute missing values in X
X_imputed = imputer.transform(X)
# Select top 3 features using SelectKBest
selector = SelectKBest(score_func=f_regression, k=3)
X_new = selector.fit_transform(X_imputed, y)
# Display the selected features
selected_features = X.columns[selector.get_support()]
print("Top 3 features selected using SelectKBest:")
print(selected_features)
Top 3 features selected using SelectKBest:
Index(['ram_capacity', 'battery_capacity', 'internal_memory'], dtype='object')
#Q34. Show the score of each feature.
# Show the score of each feature
feature_scores = selector.scores_
# Display the scores of each feature
print("Scores of each feature:")
for feature, score in zip(X.columns, feature_scores):
    print(f"{feature}: {score:.4f}")
    
Scores of each feature:
ram_capacity: 171.2325
battery_capacity: 24.8333
internal_memory: 440.2870
#Q35. Drop irrelevant columns like Model_Name.
# Drop irrelevant columns like Model_Name
df = df.drop(columns=['model_name'], errors='ignore')
# Display the first few rows after dropping irrelevant columns
print("First few rows after dropping irrelevant columns:")
print(df.head())
First few rows after dropping irrelevant columns:
  brand_name                      model  price  rating  has_5g  has_nfc  \
0    oneplus              OnePlus 11 5G  54999    89.0    True     True   
1    oneplus  OnePlus Nord CE 2 Lite 5G  19989    81.0    True    False   
2    samsung      Samsung Galaxy A14 5G  16499    75.0    True    False   
3   motorola       Motorola Moto G62 5G  14999    81.0    True    False   
4     realme         Realme 10 Pro Plus  24999    82.0    True    False   

   has_ir_blaster processor_brand  num_cores  processor_speed  ...  \
0           False      snapdragon        8.0              3.2  ...   
1           False      snapdragon        8.0              2.2  ...   
2           False          exynos        8.0              2.4  ...   
3           False      snapdragon        8.0              2.2  ...   
4           False       dimensity        8.0              2.6  ...   

   num_rear_cameras  num_front_cameras       os  primary_camera_rear  \
0                 3                1.0  android                 50.0   
1                 3                1.0  android                 64.0   
2                 3                1.0  android                 50.0   
3                 3                1.0  android                 50.0   
4                 3                1.0  android                108.0   

   primary_camera_front  extended_memory_available  extended_upto  \
0                  16.0                          0            NaN   
1                  16.0                          1         1024.0   
2                  13.0                          1         1024.0   
3                  16.0                          1         1024.0   
4                  16.0                          0            NaN   

   resolution_width  resolution_height price_per_gb  
0              1440               3216   214.839844  
1              1080               2412   156.164062  
2              1080               2408   257.796875  
3              1080               2400   117.179688  
4              1080               2412   195.304688  

[5 rows x 27 columns]
#Q36. Sort data by RAM descending.
# Sort data by RAM descending
df_sorted = df.sort_values(by='ram_capacity', ascending=False)
# Display the first few rows of the sorted data
print("First few rows of the sorted data by RAM descending:")
print(df_sorted[['brand_name', 'ram_capacity', 'price']].head())
First few rows of the sorted data by RAM descending:
    brand_name  ram_capacity  price
278       asus            18  89999
406       asus            18  75990
141       oppo            16  39999
821     lenovo            16  59999
17        oppo            16  45999
#Q37. Filter phones with RAM > 8GB and Battery > 4000mAh.
# Filter phones with RAM > 8GB and Battery > 4000mAh
filtered_phones = df[(df['ram_capacity'] > 8000) & (df['battery_capacity'] > 4000)]
# Display the filtered phones
print("Phones with RAM > 8GB and Battery > 4000mAh:")
print(filtered_phones[['brand_name', 'ram_capacity', 'battery_capacity', 'price']])
Phones with RAM > 8GB and Battery > 4000mAh:
Empty DataFrame
Columns: [brand_name, ram_capacity, battery_capacity, price]
Index: []
#Q38. Group by Brand and get the average of all numeric features
# Group by Brand and get the average of all numeric features
average_by_brand = df.groupby('brand_name').mean(numeric_only=True)
# Display the average of all numeric features by brand
print("Average of all numeric features by brand:")
print(average_by_brand)
Average of all numeric features by brand:
                    price     rating    has_5g   has_nfc  has_ir_blaster  \
brand_name                                                                 
apple        95966.521739  76.795455  0.804348  0.978261        0.000000   
asus         74709.428571  87.000000  1.000000  1.000000        0.000000   
blackview     8990.000000  67.000000  1.000000  1.000000        0.000000   
blu          14990.000000  85.000000  1.000000  1.000000        0.000000   
cat          14999.000000        NaN  0.000000  0.000000        0.000000   
cola         14999.000000  74.000000  0.000000  0.000000        0.000000   
doogee       30499.000000  86.000000  0.500000  0.500000        0.000000   
duoqin        9990.000000        NaN  0.000000  0.000000        0.000000   
gionee        6896.000000  67.000000  0.000000  0.000000        0.000000   
google       44332.571429  77.333333  0.785714  1.000000        0.000000   
honor        30301.846154  78.181818  0.769231  0.538462        0.076923   
huawei       80177.250000  80.000000  0.250000  0.750000        0.375000   
ikall         7632.333333  60.666667  0.000000  0.000000        0.000000   
infinix      14664.793103  76.285714  0.241379  0.034483        0.000000   
iqoo         30301.875000  82.218750  0.937500  0.406250        0.187500   
itel          5811.000000  61.000000  0.000000  0.000000        0.000000   
jio           7159.250000  64.000000  0.250000  0.000000        0.000000   
lava         11246.750000  74.333333  0.500000  0.000000        0.000000   
leeco        10999.000000  65.000000  0.000000  0.000000        0.000000   
leitz       124990.000000  89.000000  1.000000  1.000000        0.000000   
lenovo       53494.500000  88.000000  1.000000  1.000000        0.000000   
letv          6165.666667  60.000000  0.000000  0.000000        0.000000   
lg           63329.333333  87.000000  1.000000  1.000000        0.000000   
lyf           3940.000000  60.000000  0.000000  0.000000        0.000000   
micromax      6929.333333  64.666667  0.000000  0.000000        0.000000   
motorola     24099.923077  80.104167  0.615385  0.653846        0.000000   
nokia        24630.769231  75.300000  0.538462  0.230769        0.000000   
nothing      31195.400000  85.200000  1.000000  1.000000        0.000000   
nubia        49827.833333  84.333333  1.000000  1.000000        0.000000   
oneplus      35858.571429  82.236842  0.857143  0.785714        0.000000   
oppo         29650.034091  78.731707  0.602273  0.375000        0.000000   
oukitel      26293.000000  79.333333  0.000000  0.666667        0.000000   
poco         18479.195122  78.700000  0.634146  0.268293        0.731707   
realme       17461.422680  76.445652  0.525773  0.144330        0.000000   
redmi        15665.666667  77.333333  0.333333  0.333333        0.666667   
royole      129999.000000  87.000000  1.000000  0.000000        0.000000   
samsung      36843.030303  78.724138  0.522727  0.507576        0.007576   
sharp        59990.000000  88.000000  0.000000  1.000000        0.000000   
sony         60570.666667  81.428571  0.666667  1.000000        0.000000   
tcl           8990.000000  60.000000  0.000000  0.000000        0.000000   
tecno        14545.363636  73.677419  0.151515  0.242424        0.000000   
tesla        69999.000000  83.000000  1.000000  1.000000        0.000000   
vertu       650000.000000  62.000000  0.000000  1.000000        0.000000   
vivo         26782.387387  77.156250  0.477477  0.153153        0.036036   
xiaomi       27961.111940  78.776000  0.567164  0.276119        0.813433   
zte          40994.500000  85.500000  1.000000  1.000000        0.000000   

            num_cores  processor_speed  battery_capacity  \
brand_name                                                 
apple        6.000000         3.074375       3527.228571   
asus         8.000000         3.157143       5757.142857   
blackview    8.000000         2.300000       5180.000000   
blu          8.000000         2.400000       5000.000000   
cat          4.000000         1.300000       2000.000000   
cola         8.000000         2.200000       5000.000000   
doogee       8.000000         2.325000      14000.000000   
duoqin       8.000000         2.000000       2150.000000   
gionee       5.333333         1.996667       4100.000000   
google       8.000000         2.605000       4381.785714   
honor        8.000000         2.376923       4707.692308   
huawei       8.000000         2.685333       4360.000000   
ikall        4.000000         1.500000       5000.000000   
infinix      7.724138         2.136897       5034.482759   
iqoo         8.000000         2.738065       4750.000000   
itel         5.200000         1.420000       3944.000000   
jio          5.000000         1.550000       3575.000000   
lava         7.000000         2.225000       4750.000000   
leeco        4.000000         1.800000       5000.000000   
leitz        8.000000         3.000000       5000.000000   
lenovo       8.000000         2.920000       5300.000000   
letv         5.333333         1.900000       4000.000000   
lg           8.000000         2.546667       4433.333333   
lyf          8.000000         1.500000       3000.000000   
micromax     8.000000         1.800000       5000.000000   
motorola     8.000000         2.453846       4863.076923   
nokia        8.000000         2.116667       5028.461538   
nothing      8.000000         2.640000       4640.000000   
nubia        8.000000         3.116667       5175.000000   
oneplus      8.000000         2.673902       4759.523810   
oppo         8.000000         2.463864       4667.215909   
oukitel      8.000000         2.066667      12933.333333   
poco         7.804878         2.462750       5009.390244   
realme       8.000000         2.289072       4903.092784   
redmi        8.000000         2.233333       5000.000000   
royole       8.000000         2.840000       3905.000000   
samsung      7.939394         2.423109       4917.424242   
sharp        8.000000         2.840000       3730.000000   
sony         8.000000         2.535556       4400.000000   
tcl          8.000000         2.000000       3000.000000   
tecno        7.636364         2.148485       5333.939394   
tesla        8.000000              NaN       5000.000000   
vertu        8.000000         1.500000       2275.000000   
vivo         7.891892         2.371963       4703.738739   
xiaomi       7.910448         2.448955       4957.611940   
zte          8.000000         3.100000       4600.000000   

            fast_charging_available  fast_charging  ...  refresh_rate  \
brand_name                                          ...                 
apple                      0.695652      20.333333  ...     82.173913   
asus                       1.000000      67.857143  ...    155.571429   
blackview                  1.000000      10.000000  ...     60.000000   
blu                        1.000000            NaN  ...     60.000000   
cat                        0.000000            NaN  ...     60.000000   
cola                       1.000000      33.000000  ...     90.000000   
doogee                     1.000000      33.000000  ...     90.000000   
duoqin                     0.000000            NaN  ...     60.000000   
gionee                     0.000000            NaN  ...     60.000000   
google                     1.000000      33.800000  ...     90.000000   
honor                      0.923077      55.500000  ...     96.923077   
huawei                     0.937500      56.500000  ...     91.875000   
ikall                      0.000000            NaN  ...     60.000000   
infinix                    0.827586      42.375000  ...     81.724138   
iqoo                       1.000000      75.343750  ...    120.187500   
itel                       0.200000      18.000000  ...     60.000000   
jio                        0.250000      18.000000  ...     67.500000   
lava                       0.250000      30.000000  ...     75.000000   
leeco                      1.000000      10.000000  ...     60.000000   
leitz                      1.000000            NaN  ...    240.000000   
lenovo                     1.000000      94.000000  ...    144.000000   
letv                       0.333333      10.000000  ...     60.000000   
lg                         1.000000      25.000000  ...     60.000000   
lyf                        0.000000            NaN  ...     60.000000   
micromax                   0.000000            NaN  ...     60.000000   
motorola                   0.961538      43.936170  ...    108.692308   
nokia                      0.846154      27.454545  ...     91.384615   
nothing                    1.000000      39.600000  ...    120.000000   
nubia                      1.000000      95.000000  ...    135.500000   
oneplus                    0.976190      76.333333  ...    107.714286   
oppo                       0.852273      51.887324  ...     86.590909   
oukitel                    0.666667      49.500000  ...     80.000000   
poco                       0.926829      49.594595  ...    101.268293   
realme                     0.824742      41.912500  ...     90.123711   
redmi                      0.666667      67.000000  ...    100.000000   
royole                     0.000000            NaN  ...     60.000000   
samsung                    0.924242      24.073394  ...     88.363636   
sharp                      1.000000            NaN  ...     60.000000   
sony                       1.000000      26.625000  ...     96.666667   
tcl                        1.000000      10.000000  ...     60.000000   
tecno                      0.666667      27.954545  ...     89.090909   
tesla                      1.000000     120.000000  ...    165.000000   
vertu                      0.000000            NaN  ...     60.000000   
vivo                       0.837838      44.311111  ...     82.918919   
xiaomi                     0.917910      52.719008  ...     95.776119   
zte                        1.000000      60.000000  ...    120.000000   

            num_rear_cameras  num_front_cameras  primary_camera_rear  \
brand_name                                                             
apple               2.304348           1.000000            20.760870   
asus                2.857143           1.000000            54.000000   
blackview           2.000000           1.000000            13.000000   
blu                 4.000000           1.000000            48.000000   
cat                 1.000000           1.000000             5.000000   
cola                2.000000           1.000000            50.000000   
doogee              3.000000           1.000000           108.000000   
duoqin              1.000000           1.000000             8.000000   
gionee              1.333333           1.000000            14.000000   
google              2.142857           1.071429            31.914286   
honor               3.153846           1.076923            66.692308   
huawei              3.437500           1.200000            54.937500   
ikall               1.000000           1.000000            17.666667   
infinix             2.655172           1.000000            59.000000   
iqoo                2.937500           1.000000            53.500000   
itel                1.900000           1.000000             6.500000   
jio                 1.000000           1.000000            11.000000   
lava                3.000000           1.000000            33.750000   
leeco               2.000000           1.000000            13.000000   
leitz               2.000000           1.000000            47.200000   
lenovo              2.000000           1.000000            64.000000   
letv                2.333333           1.000000             9.666667   
lg                  3.000000           1.000000            58.666667   
lyf                 1.500000           1.000000            13.000000   
micromax            1.666667           1.000000            11.333333   
motorola            2.923077           1.038462            67.230769   
nokia               2.769231           1.000000            79.769231   
nothing             2.200000           1.000000            50.000000   
nubia               3.000000           1.000000            59.333333   
oneplus             3.047619           1.000000            53.595238   
oppo                2.727273           1.022989            45.875000   
oukitel             3.000000           1.000000            48.000000   
poco                2.926829           1.000000            54.268293   
realme              2.762887           1.030928            48.000000   
redmi               3.000000           1.000000            88.666667   
royole              3.000000           1.000000            64.000000   
samsung             3.257576           1.030303            54.242424   
sharp               3.000000           1.000000            48.000000   
sony                3.111111           1.000000            16.333333   
tcl                 1.000000           1.000000            13.000000   
tecno               2.606061           1.060606            39.272727   
tesla               3.000000           1.000000            50.000000   
vertu               1.000000           1.000000            13.000000   
vivo                2.675676           1.081081            43.194595   
xiaomi              2.925373           1.015038            65.300746   
zte                 3.500000           1.000000            57.000000   

            primary_camera_front  extended_memory_available  extended_upto  \
brand_name                                                                   
apple                  11.452174                   0.000000            NaN   
asus                   16.571429                   0.000000            NaN   
blackview               8.000000                   1.000000            NaN   
blu                    16.000000                   1.000000            NaN   
cat                     2.000000                   0.000000            NaN   
cola                   16.000000                   1.000000    1024.000000   
doogee                 32.000000                   1.000000    1536.000000   
duoqin                  2.000000                   1.000000            NaN   
gionee                  7.666667                   1.000000     256.000000   
google                  9.278571                   0.000000            NaN   
honor                  19.153846                   0.307692    1024.000000   
huawei                 19.713333                   0.687500     256.000000   
ikall                  11.333333                   1.000000     106.666667   
infinix                13.896552                   1.000000     789.333333   
iqoo                   15.500000                   0.312500    1024.000000   
itel                    5.144444                   0.700000      80.000000   
jio                     6.500000                   1.000000     384.000000   
lava                    9.250000                   1.000000     704.000000   
leeco                   5.000000                   0.000000            NaN   
leitz                  12.600000                   1.000000    1024.000000   
lenovo                 18.000000                   0.000000            NaN   
letv                    6.000000                   0.000000            NaN   
lg                     19.333333                   0.333333            NaN   
lyf                     9.000000                   1.000000      64.000000   
micromax                5.000000                   1.000000     256.000000   
motorola               24.019231                   0.615385     906.666667   
nokia                  14.692308                   1.000000     585.142857   
nothing                19.200000                   0.000000            NaN   
nubia                  13.333333                   0.000000            NaN   
oneplus                19.357143                   0.309524     768.000000   
oppo                   19.252874                   0.681818     624.390244   
oukitel                12.000000                   0.666667            NaN   
poco                   15.146341                   0.682927     777.481481   
realme                 13.896907                   0.752577     705.882353   
redmi                  12.333333                   0.666667     768.000000   
royole                 32.000000                   0.000000            NaN   
samsung                16.734848                   0.803030     952.320000   
sharp                  16.000000                   1.000000    1024.000000   
sony                    9.777778                   1.000000     853.333333   
tcl                     5.000000                   1.000000            NaN   
tecno                  15.727273                   0.727273     444.631579   
tesla                  32.000000                   0.000000            NaN   
vertu                   2.100000                   0.000000            NaN   
vivo                   21.216216                   0.702703     775.384615   
xiaomi                 15.526316                   0.649254     616.000000   
zte                    16.000000                   0.500000            NaN   

            resolution_width  resolution_height  price_per_gb  
brand_name                                                     
apple            1127.282609        2414.434783    580.902259  
asus             1080.000000        2441.142857    294.620815  
blackview         720.000000        1560.000000    140.468750  
blu              1080.000000        2460.000000    117.109375  
cat               480.000000         640.000000    937.437500  
cola             1080.000000        2400.000000    234.359375  
doogee           1080.000000        2374.000000    148.431641  
duoqin            640.000000         960.000000    156.093750  
gionee            720.000000        1573.333333    156.914062  
google           1208.571429        2610.000000    324.458705  
honor             998.769231        2190.769231    150.059195  
huawei           1271.250000        2449.000000    288.843628  
ikall             720.000000        1586.666667    160.916667  
infinix          1136.551724        2000.413793    145.296336  
iqoo             1125.000000        2501.250000    185.260376  
itel             1282.600000         736.000000    264.773438  
jio               720.000000        1440.000000    206.152344  
lava             1250.000000        1375.000000    146.451172  
leeco             720.000000        1600.000000     85.929688  
leitz            1260.000000        2730.000000    488.242188  
lenovo           1080.000000        2430.000000    150.370117  
letv              720.000000        1560.000000    161.432292  
lg               1080.000000        2460.000000    494.760417  
lyf              1080.000000        1920.000000    123.125000  
micromax          720.000000        1600.000000    139.515625  
motorola         1083.461538        2159.076923    204.255934  
nokia             938.461538        2080.615385    257.473858  
nothing          1080.000000        2400.000000    193.520312  
nubia            1092.000000        2426.666667    309.860026  
oneplus          1114.285714        2485.142857    244.993908  
oppo             1044.272727        2090.590909    193.325062  
oukitel           960.000000        2106.666667    136.429688  
poco             1044.878049        2323.463415    177.500476  
realme           1025.979381        2179.876289    179.127416  
redmi             960.000000        2150.000000    143.218750  
royole           1440.000000        1920.000000   1015.617188  
samsung          1103.303030        2272.075758    260.240959  
sharp            1440.000000        3168.000000    234.335938  
sony             1228.000000        2853.333333    299.507595  
tcl               720.000000        1440.000000    280.937500  
tecno             927.272727        2079.151515    144.075166  
tesla            1080.000000        2448.000000    136.716797  
vertu            1080.000000        1920.000000  10156.250000  
vivo             1041.045045        2125.099099    217.545960  
xiaomi           1127.776119        2295.880597    199.470820  
zte              1098.000000        2470.000000    320.269531  

[46 rows x 23 columns]
#Q39. Count how many phones have dual SIM support.
# Check available columns to find dual SIM support
print("Available columns in the dataframe:")
print(df.columns)

# If you find the correct column name for dual SIM support, replace 'dual_sim' below.
# Example: if the column is 'sim_type' and dual SIM phones are marked as 'Dual', use:
# dual_sim_count = df[df['sim_type'] == 'Dual'].shape[0]

# Placeholder for actual column name:
# dual_sim_count = df[df['<actual_column_name>'] == '<value_for_dual_sim>'].shape[0]
Available columns in the dataframe:
Index(['brand_name', 'model', 'price', 'rating', 'has_5g', 'has_nfc',
       'has_ir_blaster', 'processor_brand', 'num_cores', 'processor_speed',
       'battery_capacity', 'fast_charging_available', 'fast_charging',
       'ram_capacity', 'internal_memory', 'screen_size', 'refresh_rate',
       'num_rear_cameras', 'num_front_cameras', 'os', 'primary_camera_rear',
       'primary_camera_front', 'extended_memory_available', 'extended_upto',
       'resolution_width', 'resolution_height', 'price_per_gb'],
      dtype='object')
#Q40. Create a pairplot to examine pairwise feature trends.
# Create a pairplot to examine pairwise feature trends
sns.pairplot(df, vars=['ram_capacity', 'battery_capacity', 'internal_memory', 'price'], hue='brand_name', diag_kind='kde')
plt.title('Pairplot of Smartphone Features')
plt.show()
