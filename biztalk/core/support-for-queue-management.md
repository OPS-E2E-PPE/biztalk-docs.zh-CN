---
title: 对队列管理的支持 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60d06ba-8cf3-46d6-af59-626f12fc572a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faeb3f141e114cf1f86157084f50d0a0d490833a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278693"
---
# <a name="support-for-queue-management"></a><span data-ttu-id="1e1b3-102">队列管理支持</span><span class="sxs-lookup"><span data-stu-id="1e1b3-102">Support for Queue Management</span></span>
<span data-ttu-id="1e1b3-103">与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MQSeries 适配器你现在可以创建和删除队列远程 MQSeries 队列管理器上。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-103">With the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries adapter you can now create and delete queues remotely on the MQSeries Queue Manager.</span></span> <span data-ttu-id="1e1b3-104">这支持，因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用的远程 MQSAgent COM + 对象的通信直接与 MQSeries 队列管理器。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-104">This is supported because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses a remote MQSAgent COM+ object that communicates directly with the MQSeries Queue Manager.</span></span> <span data-ttu-id="1e1b3-105">通常，在运行时使用此 MQSAgent 从远程 MQSeries 服务器队列读取信息和向其中写入消息。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-105">Typically this MQSAgent is used at run time to read and write messages to the remote MQSeries Server queues.</span></span> <span data-ttu-id="1e1b3-106">此远程服务的客户端可以是多台 BizTalk 服务器。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-106">More than one BizTalk server can be a client of this remote service.</span></span> <span data-ttu-id="1e1b3-107">此外，队列创建和删除功能由此 MQSAgent 提供，并可以从业务流程或适配器中直接调用。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-107">Additionally, queue creation and deletion functions are provided by this MQSAgent and can be called directly from within an orchestration or adapter.</span></span> <span data-ttu-id="1e1b3-108">这样可以实现高度动态的方案：业务流程或适配器创建一个临时队列，然后向其上发送消息，在另一个队列上接收回复，最后删除这个临时队列。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-108">This allows for highly dynamic scenarios whereby the orchestration or adapter can create a temporary queue and then send a message on it, receive a reply on another queue, and finally delete the temporary queue.</span></span>  
  
## <a name="createqueue-and-deletequeue-apis"></a><span data-ttu-id="1e1b3-109">CreateQueue 和 DeleteQueue API</span><span class="sxs-lookup"><span data-stu-id="1e1b3-109">CreateQueue and DeleteQueue APIs</span></span>  
 <span data-ttu-id="1e1b3-110">CreateQueue 和 DeleteQueue API 定义如下。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-110">The CreateQueue and DeleteQueue APIs are defined as follows.</span></span>  
  
### <a name="structure-definition"></a><span data-ttu-id="1e1b3-111">结构定义</span><span class="sxs-lookup"><span data-stu-id="1e1b3-111">Structure Definition</span></span>  
  
```  
typedef enum QueueUsage {  
      Normal       = 0,  
      Transmission = 1  
} QueueUsage;  
  
typedef enum ResultCode {  
      QueueAlreadyExists                     = 0, //  no bits set  
      QueueCreated                           = 1, //  QueueCreated  
      QueueCreatedAndRemoteDefinitionUpdated = 5, //  QueueCreated | RemoteDefinitionUpdated  
      QueueAndRemoteDefinitionCreated        = 7, //  QueueCreated | RemoteDefinitionCreated | RemoteDefinitionUpdated  
      QueueDoesNotExist                      = 8, //  QueueDoesNotExist  
      QueueDeleted                           = 16 //  QueueDeleted  
} ResultCode;  
```  
  
### <a name="interface-definition"></a><span data-ttu-id="1e1b3-112">接口定义</span><span class="sxs-lookup"><span data-stu-id="1e1b3-112">Interface Definition</span></span>  
  
```  
[  
            object,  
            uuid(E90AC1A6-657B-4680-AF6A-89F11113FB8B),  
            dual,  
            nonextensible,  
            helpstring("IMQSAdmin Interface"),  
            pointer_default(unique)  
]  
interface IMQSAdmin2 : IDispatch{  
  
HRESULT CreateQueue (  
[in]BSTR queueManager,  
[in]BSTR newQueueName,  
[in]QueueUsage usage,  
[in]BSTR remoteDefinition,  
[in]BSTR remoteQName,  
[in]BSTR remoteQMgrName,  
[in]BOOL updateExistingRemoteDefinition,  
[out, retval]ResultCode* resultCode);  
  
HRESULT DeleteQueue (  
[in]BSTR queueManager,  
[in]BSTR newQueueName,  
[out, retval]ResultCode* resultCode);  
};  
  
      [  
            uuid(412AF00D-7CA8-4d2a-AFF6-F61CE2E29A0D),  
            helpstring("MQSAdmin Class")  
      ]  
      coclass MQSAdmin  
      {  
            [default] interface IMQSAdmin2;  
      };  
  
```  
  
## <a name="examples"></a><span data-ttu-id="1e1b3-113">示例</span><span class="sxs-lookup"><span data-stu-id="1e1b3-113">Examples</span></span>  
 <span data-ttu-id="1e1b3-114">完成示例 1 中的步骤可创建一个 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] C# 控制台应用程序，该程序可用于创建或删除 MQSeries Server 队列。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-114">Complete the steps in Example 1 to create a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] C# console application which can be used to create or delete MQSeries Server queues.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="1e1b3-115">示例 1</span><span class="sxs-lookup"><span data-stu-id="1e1b3-115">Example 1</span></span>  
  
##### <a name="create-a-c-console-application-to-manage-mqseries-server-queues"></a><span data-ttu-id="1e1b3-116">创建一个管理 MQSeries Server 队列的 C# 控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="1e1b3-116">Create a C# console application to manage MQSeries Server queues</span></span>  
  
1.  <span data-ttu-id="1e1b3-117">创建一个新 Visual C# 控制台应用程序中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]同名**MQSeriesQueues**。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-117">Create a new Visual C# Console Application in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] with the name **MQSeriesQueues**.</span></span>  
  
2.  <span data-ttu-id="1e1b3-118">使用以下代码替换生成的 Program.cs 文件中的所有已有代码。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-118">Replace any existing code in the Program.cs file that is generated with the code below:</span></span>  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using MQSAgentLib;  
  
    namespace MQSeriesQueues  
    {  
        class ManageQueues  
        {  
            public static void Main(string[] args)  
            {  
                // The first argument should be "c" (without quotes)  
                // to create a queue, anything else to delete a queue.  
                // The 2nd and 3rd arguments should be the name of   
                // the MQSeries Queue Manager and the name of   
                // the queue to be created or deleted for example  
                // the following usage will create the local   
                // queue testq for the Queue Manager QM_Test  
                // MQSeriesQueues c QM_Test testq  
                createordeleteQs(args[0], args[1], args[2]);  
            }  
  
            static void createordeleteQs(string Qswitch, string QMgr, string QName)  
            {   
            if ((Qswitch =="c" & (QMgr != null & QName != null)))  
                {  
                    CreateQueue(QMgr, QName);  
                }  
                else if(QMgr != null & QName != null)  
                {  
                    DeleteQueue(QMgr, QName);  
                }  
             }  
  
            static void CreateQueue(string Qmgr, string Qname)  
            {  
                MQSAdmin admin = new MQSAdmin();    
  
                ResultCode resultCode = admin.CreateQueue(Qmgr, Qname, 0, "", "", "", 0);  
  
                if ((resultCode & ResultCode.QueueCreated) == ResultCode.QueueCreated)  
                {  
                    Console.WriteLine("Queue Created.");  
                }  
                else if ((resultCode & ResultCode.QueueAlreadyExists) == ResultCode.QueueAlreadyExists)  
                {  
                    Console.WriteLine("Queue Already Exists.");  
                }  
            }  
  
            static void DeleteQueue(string Qmgr, string Qname)  
            {  
                MQSAdmin admin = new MQSAdmin();  
  
                ResultCode resultCode = admin.DeleteQueue(Qmgr, Qname);  
  
                if ((resultCode & ResultCode.QueueDeleted) == ResultCode.QueueDeleted)  
                {  
                    Console.WriteLine("Queue successfully deleted.");  
                }  
                if ((resultCode & ResultCode.QueueDoesNotExist) == ResultCode.QueueDoesNotExist)  
                {  
                    Console.WriteLine("Queue did not exist anyway!");  
                }  
            }  
  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="1e1b3-119">添加对该项目的引用**MQSAgent 1.0 类型库**。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-119">Add a reference to this project to the **MQSAgent 1.0 Type Library**.</span></span> <span data-ttu-id="1e1b3-120">**MQSAgent 1.0 类型库**位于**COM**选项卡**添加引用**对话框。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-120">The **MQSAgent 1.0 Type Library** is available on the **COM** tab of the **Add reference** dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1e1b3-121">运行此控制台应用程序的计算机中必须已经安装了 MQSAgent COM+ 组件。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-121">The MQSAgent COM+ component must be installed on the computer that you are running this console application from.</span></span> <span data-ttu-id="1e1b3-122">有关安装 MQSAgent COM + 组件的详细信息请参阅[使用 MQSAgent COM + 配置向导](../core/using-the-mqsagent-com-configuration-wizard.md)。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-122">For more information about installing the MQSAgent COM+ component see [Using the MQSAgent COM+ Configuration Wizard](../core/using-the-mqsagent-com-configuration-wizard.md).</span></span>  
  
4.  <span data-ttu-id="1e1b3-123">生成控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-123">Build the console application.</span></span>  
  
5.  <span data-ttu-id="1e1b3-124">在编译的控制台应用程序所在的目录中打开一个命令提示窗口。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-124">Open a command prompt in the same directory as the compiled console application.</span></span>  
  
6.  <span data-ttu-id="1e1b3-125">键入编译的控制台应用程序的名称和相应的参数，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="1e1b3-125">Type the name of the compiled console application with the appropriate arguments and press ENTER.</span></span> <span data-ttu-id="1e1b3-126">例如，若要删除队列**testq**的队列管理器**QM_Test**在命令提示符下键入以下文本，并按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="1e1b3-126">For example, to delete the queue **testq** for the Queue Manager **QM_Test** you would type the following text at the command prompt and press ENTER:</span></span>  
  
    ```  
    MQSeriesQueues d QM_Test testq  
    ```  
  
7.  <span data-ttu-id="1e1b3-127">若要创建队列**testq**的队列管理器**QM_Test**在命令提示符下键入以下文本，并按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="1e1b3-127">To create the queue **testq** for the Queue Manager **QM_Test** you would type the following text at the command prompt and press ENTER:</span></span>  
  
    ```  
    MQSeriesQueues c QM_Test testq  
    ```