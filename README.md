#-*- coding: utf-8 -*-

import urllib2


def inputurl():
  urlpath=raw_input(ur'输入爬虫URL：')

  while True:
       if urlpath[0:7]=='http://' or urlpath[0:8]=='https://':
          break
       else:
          urlpath=raw_input(u'输入URL格式有误重新输入：')
  return  urlpath



       

def contenttofile(url):
  filepath='c:\\hello'
  f1=open(filepath,'w+')
  response=urllib2.urlopen(url)
  if response.getcode()==200:
     print u'抓取成功到'+filepath
  count=response.read()
  f1.writelines(count)
  f1.close()


urlpath1=inputurl()
contenttofile(urlpath1)
