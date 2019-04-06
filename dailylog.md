### 3/29/19:
Followed along with the GCP Deploying Python App tutorial to get Flask app running. Successfully ran locally and deployed simple Flask app to AppEngine.

Ran into problems when I tried using Google datastore library. Locally, the datastore code wouldn't work and ran into the following problem:
"""
File "//anaconda/lib/python3.5/site-packages/google/type/latlng_pb2.py", line 22, in <module>
    serialized_pb=_b('\n\x18google/type/latlng.proto\x12\x0bgoogle.type\"-\n\x06LatLng\x12\x10\n\x08latitude\x18\x01 \x01(\x01\x12\x11\n\tlongitude\x18\x02 \x01(\x01\x42\x63\n\x0f\x63om.google.typeB\x0bLatLngProtoP\x01Z8google.golang.org/genproto/googleapis/type/latlng;latlng\xf8\x01\x01\xa2\x02\x03GTPb\x06proto3')
TypeError: __new__() got an unexpected keyword argument 'serialized_options'
""""

After searching for the error, it seemed to be a problem with mixing old and new libraries together. 

https://github.com/protocolbuffers/protobuf/issues/4716

Since my personal laptop library management is a mess (still haven't mastered conda environments or virtualenv), it was hard to debug. I tried creating a virtual environment, but ran into issues. So I created a conda environment instead, but when trying to install the google datastore library, the conda package manager couldn't find the library. So I googled how to install GCP SDK using conda, and downloaded all the CGP libraries with conda. However, after doing that, I still see the error from before.

