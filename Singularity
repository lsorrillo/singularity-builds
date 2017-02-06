BootStrap:docker
From:ubuntu:latest
%runscript
echo "This gets run when you run the image!" 
exec echo "Hello" "$@"

%post
   echo "DBG: Hello from inside the container"
   mkdir -p /code
   echo "End of the post"
