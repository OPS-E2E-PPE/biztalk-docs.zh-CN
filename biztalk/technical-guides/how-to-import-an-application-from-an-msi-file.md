---
title: "如何从.msi 文件导入应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5472df9-9f1e-42d5-82e0-cc559caf56b3
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc79413b17343ff7dbf27c90af803e7b22fb0678
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-import-an-application-from-an-msi-file"></a>如何从.msi 文件导入应用程序
BizTalk Server 管理控制台或 BTSTask 中的导入 MSI 向导可用于将 BizTalk 应用程序从.msi 文件导入到目标环境中的 BizTalk 组和各个主机组中的实例上安装应用程序。 完全导入过程将执行以下操作：  
  
-   应用程序组级别部署  
  
-   服务器级安装此应用程序。  
  
 **组级别的应用程序部署**  
  
 通过运行从 BizTalk Server 管理控制台的导入 MIS 向导或通过运行 BTSTask，可以在组中的服务器上执行的应用程序组级别的部署。 组级别部署执行以下任务：  
  
-   在组中创建应用程序和其项目  
  
-   导入驻留在.msi 程序包的绑定  
  
-   将使用其内容的所有 BizTalk Server 程序集都部署到组 BizTalk 管理数据库  
  
-   运行指定在导入时间运行的脚本。  
  
 如果你已添加到应用程序的特定于环境的绑定文件，你将需要选择你想要在导入时应用的绑定。  
  
 **服务器级别的应用程序安装**  
  
 通过双击.msi 文件本身，或执行导入 MSI 向导末尾的安装过程，可以在组中每个服务器上执行应用程序的服务器级安装。 而不是正在执行上一次每个组，它通常服务器上完成每个 BizTalk 组的成员。 服务器级安装执行以下任务：  
  
-   将安装所有 BizTalk Server 程序集和依赖程序集到全局程序集缓存的服务器，以便此计算机上具有所有运行时所需的二进制文件  
  
-   可能是解决方案的一部分，例如，业务流程发布作为 Web 服务的相关 Web 服务的回滚。  
  
-   将应用特定于计算机的更改，例如预先创建 MSMQ 队列或创建文件放置文件夹的结构和权限，这可以实现脚本的帮助。  
  
 执行.msi 文件安装应用程序时，.msi 文件将在添加或删除程序列表中，创建注册表项，并通过自动执行部署的项目以及它们的依赖项，按正确的顺序加快部署。  
  
 安装 BizTalk 应用程序的详细信息，请参阅[如何安装应用程序](../technical-guides/how-to-install-an-application.md)。  
  
 **完整的应用程序部署和安装过程**  
  
 导入 MSI 向导将部署组上的应用程序。 它不在组中的单个服务器上安装应用程序。 如果应用程序包括基于文件的项目，你需要在每个主机实例将在应用程序 （和运行应用程序依赖于此应用程序的任何计算机） 中运行的程序集上安装应用程序。 你可以执行以便在服务器上您导入 MSI 向导在上运行，但是，通过选择**运行应用程序安装向导在本地计算机上安装应用程序**显示导入成功页上的复选框导入 MSI 向导。 可以通过双击每台服务器上的.msi 文件，在上组中的其他服务器执行此操作。  
  
 如果你已准备好测试应用程序，你可以将它导入测试环境中的 BizTalk 组。 如果你的应用程序可供临时或生产环境，你可以将它导入这些环境之一。  
  
## <a name="important-considerations"></a>重要注意事项  
 当从.msi 文件导入 BizTalk 应用程序，请记住以下：  
  
-   **你必须指定你想要在标准导入过程中覆盖项目。** 如果你想要覆盖现有项目，选择选项覆盖现有项目时导入.msi 文件。  
  
-   **导入的绑定将覆盖现有的绑定。** 将包含绑定的 .msi 文件导入到现有应用程序时，现有绑定将被同名的导入绑定覆盖。 即使您没有选择在导入 .msi 文件时覆盖现有项目的选项，现有绑定也将被同名导入绑定覆盖。 如果您不希望用导出的应用程序中的绑定覆盖导入 .msi 文件的应用程序中的绑定，请不要在导出操作中选择将该绑定文件作为资源导出。 有关设置导出的资源的详细信息，请参阅[how to Export BizTalk 应用程序如何](http://go.microsoft.com/fwlink/?LinkID=154848)(http://go.microsoft.com/fwlink/?LinkID=154848)。  
  
 由于绑定在导入过程中应用，所以已应用的绑定将被同名的新绑定所覆盖。 换言之，将应用的具有特定名称的最后一个绑定生效。 导入应用程序时，绑定按如下顺序应用：  
  
1.  由 BizTalk Server 生成的、未通过绑定文件显式添加到应用程序但用户已经显式选择导出到应用程序 .msi 文件的应用程序绑定。  
  
2.  已经显式添加但尚未指定目标部署环境的绑定文件。 本组中的绑定可以按任何顺序应用。  
  
3.  已经显式添加并且具有与为导入应用程序而选的部署环境相匹配的关联目标部署环境的绑定。 本组中的绑定可以按任何顺序应用。  
  
-   **指定的主机必须存在。** 若要从.msi 文件导入应用程序，对应于在.msi 文件中包含的应用程序绑定中指定的主机的主机必须已存在于 BizTalk 组，或导入操作将失败。 此外，主机的信任级别必须匹配。  
  
-   **依赖项可以在导入操作时的重大影响。** 当你导入的应用程序具有另一个应用程序的依赖关系时，下列规则适用：  
  
    -   如果您要导入的应用程序依赖于其他应用程序中的项目，你必须从第一个应用程序到第二个应用程序中添加的引用。 应用程序和所需的项目必须已存在目标组中。 导入向导，可将引用添加。 但是，如果你使用的 BTSTask ImportApp 命令，你必须添加对导入后的应用程序的引用。 有关详细信息，请参阅[如何添加对另一个应用程序的引用](http://go.microsoft.com/fwlink/?LinkId=155011)(http://go.microsoft.com/fwlink/?LinkId=155011)。 导入向导将这些引用与组中现有应用程序相匹配，并且通过该向导您还可选择添加新引用或更改现有引用。 在 BizTalk Server 确认存在引用的应用程序时，我们建议您采取其他步骤来确认引用的应用程序包含所需项目。  
  
    -   在您安装某一应用程序时，还必须安装它所依赖的任何应用程序。 如果某个项目（如 BizTalk 程序集）包含在另一个应用程序中，而要安装的应用程序与该项目之间存在依存关系，则在安装该应用程序时，必须首先安装包含该项目的应用程序。 例如，如果您要安装应用程序 A，并且它依赖于应用程序 B 中的程序集，则您必须首先安装应用程序 B。 然后，你可以安装应用程序 a。有关安装 BizTalk 应用程序的详细信息，请参阅[如何安装应用程序](../technical-guides/how-to-install-an-application.md)。  
  
    -   如果您想要将某一应用程序导入到不同的 BizTalk 组并在该组中运行此应用程序，则还必须导入此应用程序所依赖的所有项目。 通过第一个导入的应用程序包含引用的项目中，或通过将所需的项目添加到的应用程序需要它时，可以执行此操作。 有关导入 BizTalk 应用程序的详细信息，请参阅[如何从一个.msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)。  
  
 有关详细注意事项和有关从.msi 文件导入 BizTalk 应用程序的信息，请参阅[如何导入 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154827)(http://go.microsoft.com/fwlink/?LinkID=154827)。  
  
## <a name="how-to-import-an-application"></a>如何导入应用程序  
 有关从.msi 文件导入 BizTalk 应用程序的说明，请参阅[如何导入 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154827)(http://go.microsoft.com/fwlink/?LinkID=154827)。