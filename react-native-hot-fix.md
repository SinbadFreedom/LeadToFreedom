基础功能：
1. build bundle file. OK
2. change bundle file fold.   OK
3. upload bundle.zip file.  OK
4. download bundle.zip.   OK
6. use new bundle file.   OK
7. refresh bundle file, rebuild ui.
9. google-diff match file.
8. download diff file.
9. add diffversion.
10. download diff file by version.
11. hot fix finish.

---------------------------------------------------------------------------------------------------------------
优化：
5. zip/unzip.
7. add change image url to file.
8. change download img function, hot fix image download from bundle folder.

next step:
build version control by webpage.
promote the web site.
earn money by hot fix server.



-----------------------------------------------------------------------------------------------
第二版优化

1. 读取本地package.json
	获取当前版本号,MD5校验码
2. 检测本地是否有bundle文件
	2.1 无bundle文件
			下载bundle_version_full文件,保存为bundle文件			
	2.2 有bundle文件
			本地读取
			计算MD5验证码,与package.json中的md5比较
				相同:下一步
				不相同:
					下载bundle_version_full文件					
3. 下载bundle_version_path文件
		path文件无数据
			下一步
		path文件有数据
			合并bundle_version_full和bundle_version_path
			3.1. 写入bundle文件
			3.2. 强制刷新bundle
4. 进入应用
