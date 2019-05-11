---
title: 如何从某一.msi 文件导入应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a5472df9-9f1e-42d5-82e0-cc559caf56b3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 677524c03b9cf008095546758b6c3013cf71fe19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400391"
---
# <a name="how-to-import-an-application-from-an-msi-file"></a>如何从某一.msi 文件导入应用程序
在 BizTalk Server 管理控制台或 BTSTask 导入 MSI 向导可用于 BizTalk 应用程序从.msi 文件导入到目标环境中的 BizTalk 组和组中的各个主机实例上安装应用程序。 完全导入过程将执行以下操作：  
  
- 组级别部署应用程序  
  
- 安装的服务器级别的应用程序。  
  
  **组级别应用程序部署**  
  
  通过运行导入 MIS 向导从 BizTalk Server 管理控制台或通过运行 BTSTask 的组中的服务器上执行应用程序组级别的部署。 组级别部署执行以下任务：  
  
- 在组中创建应用程序和其项目  
  
- 将绑定驻留在.msi 包中导入  
  
- 将使用其项目的所有 BizTalk Server 程序集都部署到 BizTalk 管理数据库组  
  
- 运行指定要在导入时运行脚本。  
  
  如果已将特定于环境的绑定文件添加到应用程序，您将必须选择你想要在导入时应用的绑定。  
  
  **服务器级别的应用程序安装**  
  
  通过双击.msi 文件本身，或执行安装过程中的导入 MSI 向导结束时，可以在组中每个服务器上执行服务器级别安装应用程序。 而不是正在进行上一次每个组，它通常是在每个 BizTalk server 组的成员。 服务器级别安装将执行以下操作：  
  
- 以便此计算机上具有所有所需的运行时的二进制文件安装到全局程序集缓存中的服务器的所有 BizTalk Server 程序集和依赖程序集  
  
- 发布了可能的解决方案的一部分，例如，业务流程发布为 Web 服务相关 Web 服务。  
  
- 应用特定于计算机的更改，例如预创建 MSMQ 队列，或创建文件放置文件夹结构和权限，可以使用脚本的帮助。  
  
  在执行时要安装的应用程序的.msi 文件，.msi 文件中的添加或删除程序列表中，创建多个注册表项并加速并部署自动部署的项目和正确的顺序及其依赖项。  
  
  安装 BizTalk 应用程序的详细信息，请参阅[如何安装应用程序](../technical-guides/how-to-install-an-application.md)。  
  
  **完整的应用程序部署和安装过程**  
  
  导入 MSI 向导将部署组上的应用程序。 它不在组中的单个服务器上安装应用程序。 如果应用程序包含基于文件的项目，您需要将应用程序 （和运行应用程序依赖于此应用程序的任何计算机） 中运行的程序集的每个主机实例上安装应用程序。 您可以执行以便在服务器上导入 MSI 向导上运行，但是，通过选择**运行应用程序安装向导以在本地计算机上安装应用程序**通过显示的导入成功页上的复选框导入 MSI 向导。 可以仍使用此组中的其他服务器上通过双击每个这些服务器上的.msi 文件。  
  
  如果你已准备好测试应用程序，可以将它导入在测试环境中的 BizTalk 组。 如果应用程序是用于过渡或生产准备就绪，您可以将它导入这些环境之一。  
  
## <a name="important-considerations"></a>重要注意事项  
 当从.msi 文件导入 BizTalk 应用程序，请记住以下：  
  
- **必须指定你想要在标准导入过程中都覆盖项目。** 如果你想要覆盖现有项目，选择导入.msi 文件时覆盖现有项目的选项。  
  
- **导入的绑定覆盖现有绑定。** 导入一个包含绑定到现有应用程序的.msi 文件时，将被导入具有相同名称的绑定覆盖现有绑定。 这是这种情况，即使你未选择覆盖现有项目时导入.msi 文件的选项。 如果不希望要导出到其中导入.msi 文件的应用程序中的绑定覆盖应用程序中的绑定，然后应作为资源导出导出操作期间不选择绑定文件。 有关设置导出的资源的详细信息，请参阅[如何导出 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkID=154848)(http://go.microsoft.com/fwlink/?LinkID=154848)。  
  
  当导入过程中应用绑定时，已应用的绑定将覆盖具有相同名称的新绑定。 换而言之，具有特定名称的最后一个绑定，应用将生效。 导入应用程序时，绑定按以下顺序应用：  
  
1.  应用程序绑定由 BizTalk Server 生成的未显式添加到应用程序通过绑定文件，但已经显式选择导出到应用程序.msi 文件的用户。  
  
2.  已显式添加，并且没有指定目标部署环境的绑定文件。 在此集中的绑定可以按任何特定顺序应用。  
  
3.  绑定已显式添加的且具有相关联的目标部署环境为应用程序导入选择的部署环境相匹配。 在此集中的绑定可以按任何特定顺序应用。  
  
- **指定的主机必须存在。** 若要从某一.msi 文件导入应用程序，主机相对应的.msi 文件中包含的应用程序绑定中指定的主机必须已存在于 BizTalk 组或导入操作将失败。 此外，主机的信任级别必须与匹配。  
  
- **依赖项有很大影响后导入操作。** 导入程序依赖于另一个应用程序的应用程序时，以下规则适用：  
  
  -   如果您要导入的应用程序依赖于另一个应用程序中的某个项目，你必须从第一个应用程序到第二个应用程序添加的引用。 应用程序和所需的项目必须已存在于目标组。 导入向导，可将引用添加。 但是，如果使用 BTSTask 的 ImportApp 命令，必须添加对导入后的应用程序的引用。 有关详细信息，请参阅[如何添加对另一个应用程序的引用](http://go.microsoft.com/fwlink/?LinkId=155011)(http://go.microsoft.com/fwlink/?LinkId=155011)。 导入向导匹配对组中的现有应用程序的引用，并可选择要添加新引用或更改现有引用。 虽然 BizTalk Server 验证引用的应用程序存在，我们建议您采取额外的步骤来验证引用的应用程序包含所需的项目。  
  
  -   在安装应用程序时，还必须安装它所依赖的任何应用程序。 当安装某个项目，如 BizTalk 程序集，其中包含在另一个应用程序中，具有一个依赖项的应用程序时必须首先安装包含该项目的应用程序。 例如，如果你想要安装应用程序 A，并且取决于应用程序 B 中的程序集，您必须首先安装应用程序 B。 然后，你可以安装应用程序 a。有关安装 BizTalk 应用程序的详细信息，请参阅[如何安装应用程序](../technical-guides/how-to-install-an-application.md)。  
  
  -   如果你想要将应用程序导入不同的 BizTalk 组并在该组中运行它，您还必须导入此应用程序所依赖的所有项目。 通过首先导入的应用程序包含所引用的项目，或通过将所需的项目添加到需要它的应用程序时，可以执行此操作。 有关导入 BizTalk 应用程序的详细信息，请参阅[如何从一个.msi 文件导入应用程序](../technical-guides/how-to-import-an-application-from-an-msi-file.md)。  
  
  有关详细注意事项和从某一.msi 文件导入 BizTalk 应用程序有关的信息，请参阅[导入 BizTalk 应用程序的方式](http://go.microsoft.com/fwlink/?LinkID=154827)(http://go.microsoft.com/fwlink/?LinkID=154827)。  
  
## <a name="how-to-import-an-application"></a>如何导入应用程序  
 有关从某一.msi 文件导入 BizTalk 应用程序的说明，请参阅[导入 BizTalk 应用程序的方式](http://go.microsoft.com/fwlink/?LinkID=154827)(http://go.microsoft.com/fwlink/?LinkID=154827)。