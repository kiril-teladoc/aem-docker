# Use the previously created aem-base-image
FROM aem-base-image

# Expose AEM Publish in port 4503
EXPOSE 4503

# Rename Quickstart jar file for publish instance
RUN mv cq-quickstart.jar aem-publish-p4503.jar 

# Start the aem-publish container
ENTRYPOINT ["java", "-Xmx1536M", "-jar", "aem-publish-p4503.jar", "-nofork"]