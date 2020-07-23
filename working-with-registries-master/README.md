# Working with registries and ImageStreams

To get to a complete solution, you will need to use steps you have executed on previous days as well. Review the homework assignments from day 3 and 4 for any hints that you need.

Deploy an application based on the following requirements:
* The project name for OpenShift is (your current project name)-apollo.
    * For example, my current project assigned to me is "kstephe-us", so my project for this exercise would be kstephe-us-apollo
* The \*apollo should be owned by you.
* The application name for OpenShift is lunar.
* The application should be accessible from the outside
* The image stream that the application will be deployed from should be in OpenShift project (your current project name)-orion and be named solar
* The image stream should point to quay.io/redhattraining/hello-world-nginx for the container image

To test the application curl the route and you should receive “Hello, world from nginx!”
