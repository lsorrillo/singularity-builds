BootStrap:docker
From:centos:latest
%runscript
echo "This gets run when you run the image!" 
exec echo "Hello" "$@"

%post
   echo "Hello from inside the container"
   mkdir -p /code
   echo "End of the post"
