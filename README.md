# IS6941
#!/usr/bin/env python
#coding: utf-8

from github import Github
import requests

#file path on the respority
file_path="README.md"

#enter the token generated from github
token=input("Please enter your token:")
g=Github(token)

#respority format:author/project
repo=g.get_repo("18520339/facebook-data-extraction")
#Get file from branch
file=repo.get_contents(file_path,ref="master")

#decode the content in utf-8
data=file.decoded_contene.decode("utf-8")

#save to local path
md_file="READ.md"
with open(md_file,';w',encoding='utf-8') as f:
f.write(data)

print("done!")
