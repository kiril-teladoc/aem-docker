# Use the previously created aem-base-image
FROM aem-base-image

# Expose AEM author in port 4502
EXPOSE 4502

# Rename Quickstart jar file for author instance
RUN mv cq-quickstart.jar aem-author-p4502.jar 

# Start the aem-author container
ENTRYPOINT ["java", "-Xmx1536M", "-jar", "aem-author-p4502.jar", "-nofork"]