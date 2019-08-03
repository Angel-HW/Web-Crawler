import urllib.request
import re

def open_url(url):
    req = urllib.request.Request(url)
    req.add_header('User-Agent','Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/75.0.3770.100 Safari/537.36')
    response = urllib.request.urlopen(req)
    html = response.read().decode('utf-8')
    #print(html)
    return html

def download_img(html):
     p = r'<img class="BDE_Image" src="([^"]+\.jpg)"'
     imglist = re.findall(p,html)
     '''
     print('---------p-------')
     print(len(imglist))
     for i in imglist:
         print(i)
     '''
     name = 1
     for each in imglist:
        file_name = 'E:\Study\programingtools\py\program\pciture\\'+str(name)+'.jpg'
        name+=1
        urllib.request.urlretrieve(each,file_name,None)
     
     
if __name__=='__main__':
    print('请输入需要爬取的网站链接：')
    url = input()
    #url='https://tieba.baidu.com/p/6182329359'
    print(url)
    print('正在爬取，请稍等……')
    download_img(open_url(url))
    print('图片爬取成功！')
