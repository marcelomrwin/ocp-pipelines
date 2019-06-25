FROM registry.access.redhat.com/dotnet/dotnet-21-jenkins-slave-rhel7

RUN /opt/rh/rh-dotnet21/root/usr/bin/dotnet tool install --global dotnet-sonarscanner
RUN chmod 777 -R /home/jenkins/.dotnet/tools

USER 0

RUN ln -s /home/jenkins/.dotnet/tools/dotnet-sonarscanner /opt/rh/rh-dotnet21/root/usr/bin/dotnet-sonarscanner

RUN chmod 777 -R /opt/rh/rh-dotnet21/root/usr/bin
RUN chown -R 1001:0 /opt/rh/rh-dotnet21/root/usr/bin
RUN chmod 777 -R /home/jenkins/.nuget/

USER 1001

RUN cd ~