### 1.1

pts1 shape: (3439, 2)
pts2 shape: (3439, 2)
A shape: (3439, 9)

Fundamental matrix F:
[[ 0.          0.00000111  0.00041297]
 [-0.0000009  -0.00000007  1.23013634]
 [-0.00125991 -1.23001705  1.        ]]

 ### 1.2

 Test point in image 1: (np.float64(55.528594970703125), np.float64(740.7119140625))
Matched point in image 2: (14, 740)
SSD error: 3226.0

1. Point in image 1: (np.float64(55.528594970703125), np.float64(740.7119140625)), Matched point in image 2: (14, 740), SSD error: 3226.0
2. Point in image 1: (np.float64(1035.0772705078125), np.float64(1313.0745849609375)), Matched point in image 2: (846, 1313), SSD error: 10568.0
3. Point in image 1: (np.float64(1606.6195068359375), np.float64(478.0445556640625)), Matched point in image 2: (1533, 478), SSD error: 14932.0
4. Point in image 1: (np.float64(1947.13232421875), np.float64(283.013671875)), Matched point in image 2: (1876, 283), SSD error: 18436.0
5. Point in image 1: (np.float64(2934.146484375), np.float64(616.3624267578125)), Matched point in image 2: (2839, 617), SSD error: 12571.0


img1_x	img2_x	img1_y	img2_y	ssd
0	55.528595	14	740.711914	740	3226.0
1	1035.077271	846	1313.074585	1313	10568.0
2	1606.619507	1533	478.044556	478	14932.0
3	1947.132324	1876	283.013672	283	18436.0
4	2934.146484	2839	616.362427	617	12571.0

### 1.3

K1: [[3979.911    0.    1244.772]
 [   0.    3979.911 1019.507]
 [   0.       0.       1.   ]]
K2: [[3979.911    0.    1369.115]
 [   0.    3979.911 1019.507]
 [   0.       0.       1.   ]]
Essential matrix E:
[[    0.01320554    17.57988815     6.15103907]
 [  -14.27269502    -1.16108987  4891.07174026]
 [   -8.66592238 -4889.60824123     0.44961116]]


 ### 1.4

P1 shape: (3, 4), P2 shape: (3, 4)

Triangulated 3D points shape: (3439, 3)
[[-1383.56561795  -325.02590969  4630.22774349]
 [-1387.77054882  -195.38590888  4657.98118385]
 [-1387.77054882  -195.38590888  4657.98118385]
 [-1345.21358302  -358.9019112   4581.78401233]
 [-1326.02556368  -347.86806563  4554.94302021]]

Mean reprojection error: 0.1700
Num of points satisfying chirality: 3439 out of 3439
All points satisfy chirality: True

### 1.5

Valid 3D points: 1.0
Mean error of valid points: 0.1700 px

### 2.1

Rectification matrix M1:
[[1. 0. 0.]
 [0. 1. 0.]
 [0. 0. 1.]]
Rectification matrix M2:
[[1. 0. 0.]
 [0. 1. 0.]
 [0. 0. 1.]]

### 2.2

Invalid ratio: 29.61%
Raw disparity range: 0.56 to 319.00

### 2.3

Scaled focal length (f): 4178.69 pixels
Baseline (b): 193.001000 in the provided translation units
Valid depth ratio: 70.39%
Depth range: 2528.19 to 1433763.12 in the provided translation units


