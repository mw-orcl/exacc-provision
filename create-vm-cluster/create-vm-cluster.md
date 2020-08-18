# Create a VM Cluster

The VM cluster provides a link between your Exadata Cloud@Customer infrastructure and Oracle Database.

Before you can create any databases on your Exadata Cloud@Customer infrastructure, you must create a VM cluster network, and you must associate it with a VM cluster. Each Exadata Cloud@Customer infrastructure deployment can support one VM cluster network and associated VM cluster.

## Prerequisites

To create a VM cluster, ensure that you that have:

- Active Exadata infrastructure available to host the VM cluster.
- A validated VM cluster network available for the VM cluster to use.
- SSH Key pair use to access the VM cluster compute nodes.

## Create a VM Cluster

1. Open the navigation menu. Under **Oracle Database**, click **Exadata Cloud@Customer**. Choose the **Region** and **Compartment** that contains your Exadata infrastructure. Click **VM Clusters**.

   ![image-20200815142601703](images/image-20200815142601703.png)

   

2. Click **Create VM Cluster**.

   ![image-20200815143113443](images/image-20200815143113443.png)

   

3. Provide the requested information in the Create VM Cluster page：

 - **Choose a compartment:** From the list of available compartments, choose the compartment that you want to contain the VM cluster.

 - **Provide the display name:** The display name is a user-friendly name that you can use to identify the VM cluster. 

 - **Select Exadata Cloud@Customer Infrastructure:** From the list, choose the Exadata infrastructure to host the VM cluster. You are not able to create a VM cluster without available and active Exadata infrastructure.

 - **Select a VM Cluster Network:** From the list, choose a VM cluster network definition to use for the VM cluster. You must have an available and validated VM cluster network before you can create a VM cluster.

 - **Choose the Oracle Grid Infrastructure version:** From the list, choose the of Oracle Grid Infrastructure release that you want to install on the VM cluster.

  ![image-20200818111718938](images/image-20200818111718938.png)![image-20200818111828341](images/image-20200818111828341.png)

 - **Configure VM cluster**: You need configure the vm cluster with OCPU, memory and local file system size. 

   - **Specify the OCPU count per VM:** Specify the OCPU count for each individual VM. The count must be a value greater than 2 and up to the number of remaining unallocated CPU cores.
   - **Requested OCPU count for the VM Cluster:** Displays the total number of CPU cores that are allocated to the VM cluster based on the value you specified in the **Specify the OCPU count per VM** field.
   - **Specify the memory per VM (GB):** Specify the memory for each individual VM. The vaule must be a multiple of 1 GB and is limited by the available memory on the Exadata infrastructure.
   - **Requested memory for the VM Cluster (GB):** Displays the total amount of memory that are allocated to the VM cluster based on the value you specified in the Specify the memory per VM (GB) field.
   - **Specify the local file system size per VM (GB):** Specify the size for each individual VM. The value must be a multiple of 1 GB and is limited by the available size of the file system on the X8-2 and X7-2 infrastructures.

  ![image-20200815151143269](images/image-20200815151143269.png)

  

 - **Configure the Exadata Storage:** The following settings define how the Exadata storage is configured for use with the VM cluster. These settings cannot be changed after creating the VM cluster.

   - **Specify Usable Exadata Storage:** Specify the size for each individual VM. The minimum recommended size is 2 TB.
   - **Allocate Storage for Exadata Snapshots:** Check this option to create a sparse disk group, which is required to support Exadata snapshot functionality. Exadata snapshots enable space-efficient clones of Oracle databases that can be created and destroyed very quickly and easily.
   - **Allocate Storage for Local Backups:** Check this option to configure the Exadata storage to enable local database backups. If you select this option, more space is allocated to the RECO disk group to accommodate the backups. If you do not select this option, you cannot use local Exadata storage as a backup destination for any databases in the VM cluster.

  ![image-20200815151535536](images/image-20200815151535536.png)

  

 - **Add SSH Key:** Specify the public key portion of an SSH key pair that you want to use to access the VM cluster compute nodes. You can upload a file containing the key, or paste the SSH key string.

 - **Choose a license type:**

   - **Bring Your Own License (BYOL):** Select this option if your organization already owns Oracle Database software licenses that you want to use on the VM cluster.
   - **License Included:** Select this option to subscribe to Oracle Database software licenses as part of Exadata Cloud@Customer.

  ![image-20200815151814776](images/image-20200815151814776.png)

  

4. Click **Show Advanced Options**. The default time zone for the Exadata Infrastructure is UTC, but you can specify a different time zone. 

  ![image-20200815152327965](images/image-20200815152327965.png)

  

5. Click **Create VM Cluster**. The VM Cluster Details page is now displayed. While the creation process is running, the state of the VM cluster is **Pending**. When the VM cluster creation process completes, the state of the VM cluster changes to **Available**.

  ![image-20200815152455235](images/image-20200815152455235.png)

  

6. Now the VM Cluster is ready, you can move on to the next lab.



