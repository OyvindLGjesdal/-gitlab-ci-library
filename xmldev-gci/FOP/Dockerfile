FROM oyvindlg/gitlab-ci-library:xmldev-el9
USER root
ENV FOP_VERSION 2.10
ENV FOP_HOME /opt/fop
RUN microdnf install -y tar gzip git \ 
    dejavu-sans-mono-fonts dejavu-sans-fonts dejavu-serif-fonts fontconfig \
    fontpackages-filesystem libfontenc xorg-x11-fonts-misc xorg-x11-fonts-Type1 && \
mkdir $FOP_HOME && \
cd $FOP_HOME && \
curl -o fop.tar.gz https://archive.apache.org/dist/xmlgraphics/fop/binaries/fop-${FOP_VERSION}-bin.tar.gz && \
tar --extract --file=fop.tar.gz --strip-components=2 fop-${FOP_VERSION}/fop && \
 rm fop.tar.gz && \
ls -alh
COPY build.xml ${FOP_HOME}/build.xml
USER 10001

