To deploy the app to k8s use commands:

    cd ./.infrastructure

    kubectl apply -f deployment.yml
    
As the app will be the only app deployed on server, we can allocate to the app a lot of resources. In hpa.yml, I put the both utilizations to 80 percents because it is the highest point after which there is a big chance of using all allowed resources. In deployment.yml, I put such numbers because it is minimal numbers which satisfies requirements.

To access the app use a command:

    kubectl port-forward pod/todoapp 8080:8080