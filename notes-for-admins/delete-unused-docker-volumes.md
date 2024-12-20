# Delete Unused Docker Volumes

## How to Delete Unused Docker Volumes from Portainer UI

This guide explains how to delete unused Docker volumes using the Portainer UI. Removing unused volumes helps free up disk space and maintain a clean environment.

***

### Prerequisites

* Access to Portainer's web interface.
* Admin or sufficient permissions to manage Docker volumes.

***

### Steps to Delete Unused Docker Volumes

1. **Log in to Portainer**
   * Open your web browser and navigate to the Portainer URL.
   * [Login to Qube](../access-qube/login-to-qube.md) with your credentials.
2.  **Navigate to the Volumes Section**

    * From the Portainer dashboard, select the **Environment** where you want to manage volumes (i.e. [connect-to-your-machine.md](../access-qube/connect-to-your-machine.md "mention")).
    * In the left-hand menu, click on **Volumes** under the **Resources** section.

    <figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
3. **Identify Unused Volumes**
   * In the Volumes list, look for volumes marked as **Unused**. These are volumes that are not currently attached to any container.
4. **Delete Unused Volumes**
   * To delete individual volumes:
     * Click the **Trash** icon next to the unused volume.
     * Confirm the deletion in the prompt that appears.
   * To delete multiple volumes:
     * Check the boxes next to the volumes you want to delete.
     * Click the **Remove** button at the top of the list.
     * Confirm the deletion in the prompt.
5. **Verify Deletion**
   * After deletion, refresh the Volumes page to ensure the unused volumes are removed.

***

### Notes

* **Caution:** Deleting a volume permanently removes its data. Ensure the volume is no longer needed before deletion.
* If you cannot delete a volume, verify that no containers or services are using it.

***
