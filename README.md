Import pandas as pdfrom math import sqrt
Def load_data(file):
data = pd.read_csv(file)returndata
Def get_rating(data, index):
result =[]
Result=data[data["user_id"]==index]["rating"].values
Return resultdefcomputer_distance(rating_index, rating_me):
#x[1,1,0,1]
#y[5,5,0,5]
sum = 0
foriinrange(0, 4):
sum = sum+ (rating_index[i]-rating_me[i])*(rating_index[i]-rating_me[i])returnsqrt(sum)
Def get_distance_with_me(data, index):
rating_index = []
rating_me = []
rating_index = get_rating(data, index)
print(rating_index)
result = computer_distance(rating_index, rating_me)
Return result
Return result
Def find_min_distance(map):
index = 0
distance = 0
min = 99999
For key, valueinmap.items():
print("key: %s , vlalue:%s"%(key, value))
ifmin>value:
min = value
index = key
distance = min
Return index, distance
file = "E:\\movie.csv"
data = load_data(file)
print(data[data["user_id"]==1]["rating"].values)
map = {}
foriinrange(1, 4):
map[i] = get_distance_with_me(data, i)
print(map[i])
index, distance = find_min_distance(map) 
print("第%s人跟我的距离最接近，他的值是%s"%(index, distance))
[1 1 0 1]
[1 1 0 1]
6.928203230275509
[4 0 2 1]
6.782329983125268
[3 4 1 4]
2.6457513110645907
key: 1 , vlalue:6.928203230275509
key: 2 , vlalue:6.782329983125268
key: 3 , vlalue:2.6457513110645907
第3人跟我的距离最接近，他的值是2.6457513110645907
sum = 0
For i in range(1, 11):
sum = sum+i
print(sum)
