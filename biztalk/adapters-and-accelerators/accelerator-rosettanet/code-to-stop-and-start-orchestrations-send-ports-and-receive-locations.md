---
title: 停止和启动业务流程，发送端口，并以编程方式接收位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- send ports, examples
- SDK samples, send ports
- examples, send ports
- SDK samples, orchestrations
- receive locations
- SDK samples, receive locations
- examples, receive locations
ms.assetid: 1c06e14d-44ec-4292-a2c2-ee2c8d07d948
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96b914129d9afb6dfd542f00a302e739e34dafbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210877"
---
# <a name="stopping-and-starting-orchestrations-send-ports-and-receive-locations-programmatically"></a><span data-ttu-id="f1bda-102">停止和启动业务流程，发送端口，并以编程方式接收位置</span><span class="sxs-lookup"><span data-stu-id="f1bda-102">Stopping and Starting Orchestrations, Send Ports, and Receive Locations Programmatically</span></span>
<span data-ttu-id="f1bda-103">本主题提供了以编程方式停止和启动业务流程、发送端口和接收位置的示例代码。</span><span class="sxs-lookup"><span data-stu-id="f1bda-103">This topic provides sample code for programmatically stopping and starting orchestrations, send ports, and receive locations.</span></span> <span data-ttu-id="f1bda-104">您可以对所有业务流程、发送端口和接收位置以组或个人身份执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="f1bda-104">You can perform these actions on all orchestrations, send ports, and receive locations as a group or individually.</span></span> <span data-ttu-id="f1bda-105">可使程序包含这些代码，以便动态地执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="f1bda-105">You can include this code in a program to perform these actions dynamically.</span></span> <span data-ttu-id="f1bda-106">执行这些操作是在图形用户界面中在设计时[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]，或在运行时在 BizTalk 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f1bda-106">You perform these actions in the graphical user interface at design time in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)], or at run time in the BizTalk Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1bda-107">对于启动或停止业务流程的代码，您无需指定业务流程、发送端口或接收位置。</span><span class="sxs-lookup"><span data-stu-id="f1bda-107">For the code to start and stop orchestrations, you do not have to designate the orchestrations, send ports, or receive locations.</span></span> <span data-ttu-id="f1bda-108">示例代码对所有业务流程执行操作、 发送端口和接收位置的[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]向上安装组。</span><span class="sxs-lookup"><span data-stu-id="f1bda-108">The sample code performs the action on all orchestrations, send ports, and receive locations that [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] installed at set up.</span></span> <span data-ttu-id="f1bda-109">对于作用于单一业务流程、发送端口或接收位置的代码，请添加一个参数，指明代码要针对哪个业务流程、发送端口或接收位置来运行。</span><span class="sxs-lookup"><span data-stu-id="f1bda-109">For the code that acts on a single orchestration, send port, or receive location, add a parameter indicating on which orchestration, send port, or receive location you want the code to run.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="f1bda-110">演示</span><span class="sxs-lookup"><span data-stu-id="f1bda-110">Demonstrates</span></span>  
 <span data-ttu-id="f1bda-111">本主题中的示例代码包括执行以下功能的各个代码段：</span><span class="sxs-lookup"><span data-stu-id="f1bda-111">The sample code in this topic includes separate code sections to do the following:</span></span>  
  
-   <span data-ttu-id="f1bda-112">启动业务流程—启动所有发送端口和接收位置，并登记和启动所有业务流程</span><span class="sxs-lookup"><span data-stu-id="f1bda-112">Start orchestrations—start all the send ports and receive locations, and enlist and start all orchestrations</span></span>  
  
-   <span data-ttu-id="f1bda-113">停止业务流程—取消登记所有业务流程，取消登记所有发送端口，并禁用所有接收位置</span><span class="sxs-lookup"><span data-stu-id="f1bda-113">Stop orchestrations—unenlist all orchestrations, unenlist all send ports, and disable all receive locations</span></span>  
  
-   <span data-ttu-id="f1bda-114">启动单个发送端口</span><span class="sxs-lookup"><span data-stu-id="f1bda-114">Start a single send port</span></span>  
  
-   <span data-ttu-id="f1bda-115">启用单个接收位置</span><span class="sxs-lookup"><span data-stu-id="f1bda-115">Enable a single receive location</span></span>  
  
-   <span data-ttu-id="f1bda-116">取消登记单个发送端口</span><span class="sxs-lookup"><span data-stu-id="f1bda-116">Unenlist a single send port</span></span>  
  
-   <span data-ttu-id="f1bda-117">禁用单个接收位置</span><span class="sxs-lookup"><span data-stu-id="f1bda-117">Disable a single receive location</span></span>  
  
-   <span data-ttu-id="f1bda-118">启动单个业务流程</span><span class="sxs-lookup"><span data-stu-id="f1bda-118">Start a single orchestration</span></span>  
  
-   <span data-ttu-id="f1bda-119">取消登记单个业务流程</span><span class="sxs-lookup"><span data-stu-id="f1bda-119">Unenlist a single orchestration</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1bda-120">示例</span><span class="sxs-lookup"><span data-stu-id="f1bda-120">Example</span></span>  
 <span data-ttu-id="f1bda-121">本主题中的示例代码包括执行“演示”部分中列出的功能的各个代码段。</span><span class="sxs-lookup"><span data-stu-id="f1bda-121">The sample code in this topic includes separate code sections to do the functions listed in the "Demonstrates" section.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.ExplorerOM;  
  
namespace Control  
{  
class Control  
{  
BtsCatalogExplorer bceExplorer;  
string[] sOrchestrations;  
string[] sReceiveLocations;  
string[] sSendPorts;  
  
[STAThread]  
static void Main(string[] args)  
{  
Control controlInstance = new Control();  
if(args.Length>0 && args[0].ToUpper()=="STOP")  
controlInstance.StopOrchestrations();  
else  
controlInstance.StartOrchestrations();  
}  
  
public Control()  
{  
bceExplorer = new BtsCatalogExplorer();  
//Edit the following connection string to point to the correct database and server  
bceExplorer.ConnectionString = "Integrated Security=SSPI;database=BizTalkMgmtDb;server=localhost";  
  
//Orchestrations  
sOrchestrations = new string[9];  
sOrchestrations[0]="Microsoft.Solutions.BTARN.CommonTypes.OdxTypes,Microsoft.Solutions.BTARN.CommonTypes, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[1]="Microsoft.Solutions.BTARN.CommonTypes.SendExceptionToLOB,Microsoft.Solutions.BTARN.CommonTypes, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[2]="Microsoft.Solutions.BTARN.CommonTypes.SendExceptionToPrivateProcess,Microsoft.Solutions.BTARN.CommonTypes, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[3]="Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess,Microsoft.Solutions.BTARN.PrivateInitiator, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[4]="Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess,Microsoft.Solutions.BTARN.PrivateResponder, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[5]="Microsoft.Solutions.BTARN.PublicInitiator.PublicInitiatorV11,Microsoft.Solutions.BTARN.PublicInitiator, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[6]="Microsoft.Solutions.BTARN.PublicInitiator.PublicInitiatorProcess,Microsoft.Solutions.BTARN.PublicInitiator, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[7]="Microsoft.Solutions.BTARN.PublicResponder.PublicResponderV11,Microsoft.Solutions.BTARN.PublicResponder, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[8]="Microsoft.Solutions.BTARN.PublicResponder.PublicResponderProcess,Microsoft.Solutions.BTARN.PublicResponder, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
  
//Send Ports  
sSendPorts = new string[2];  
sSendPorts[0]="PrivateInitiator_To_LOB";  
sSendPorts[1]="PrivateResponder_To_LOB";  
  
//Receive Locations  
sReceiveLocations = new string[4];  
sReceiveLocations[0]="LOB_To_PrivateInitiator";  
sReceiveLocations[1]="LOB_To_PrivateResponder";  
sReceiveLocations[2]="RNIF_Async_Receive";  
sReceiveLocations[3]="RNIF_Sync_Receive";  
}  
  
public void StartOrchestrations()  
{     
bool bSuccess=true;  
  
//Start all the send ports  
for(int i=0;i<sSendPorts.Length;i++)  
{  
Console.WriteLine("Starting send port: " + sSendPorts[i]);  
bSuccess=StartSendPort(sSendPorts[i]);  
}  
  
//Start all the receive locations  
for(int i=0;i<sReceiveLocations.Length;i++)  
{  
Console.WriteLine("Enabling receive location: " + sReceiveLocations[i]);  
bSuccess=EnableReceiveLocation(sReceiveLocations[i]);  
}  
  
//Enlist and start all orchestrations  
for(int i=0;i<sOrchestrations.Length;i++)  
{  
Console.WriteLine("Starting orchestration: " + sOrchestrations[i].Split(',')[0]);  
bSuccess=StartOrchestration(sOrchestrations[i]);  
}  
  
if(bSuccess)  
Console.WriteLine("All artifacts successfully started");  
else  
Console.WriteLine("Not all artifacts were started");  
}  
  
public void StopOrchestrations()  
{     
bool bSuccess=true;  
  
//Unenlist all orchestrations  
for(int i=sOrchestrations.Length-1;i>=0;i--)  
{  
Console.WriteLine("Unelisting orchestration: " + sOrchestrations[i].Split(',')[0]);  
bSuccess=UnenlistOrchestration(sOrchestrations[i]);  
}  
  
//Unenlist all the send ports  
for(int i=sSendPorts.Length-1;i>=0;i--)  
{  
Console.WriteLine("Unenlisting send port: " + sSendPorts[i]);  
bSuccess=UnenlistSendPort(sSendPorts[i]);  
}  
  
//Disable all the receive locations  
for(int i=sReceiveLocations.Length-1;i>=0;i--)  
{  
Console.WriteLine("Disabling receive location: " + sReceiveLocations[i]);  
bSuccess=DisableReceiveLocation(sReceiveLocations[i]);  
}  
  
if(bSuccess)  
Console.WriteLine("All artifacts successfully stopped");  
else  
Console.WriteLine("Not all artifacts were stopped");  
}  
  
public bool StartSendPort(string sSendPortName)  
{  
try  
{  
SendPort sp = bceExplorer.SendPorts[sSendPortName];  
sp.Status = PortStatus.Started;  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
public bool EnableReceiveLocation(string sReceivePortName)  
{  
try  
{  
ReceivePort rp = bceExplorer.ReceivePorts[sReceivePortName];  
              foreach(ReceiveLocation rl in rp.ReceiveLocations)  
rl.Enable = true;  
  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
public bool UnenlistSendPort(string sSendPortName)  
{  
try  
{  
SendPort sp = bceExplorer.SendPorts[sSendPortName];  
sp.Status = PortStatus.Bound;  
  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
public bool DisableReceiveLocation(string sReceivePortName)  
{  
try  
{  
ReceivePort rp = bceExplorer.ReceivePorts[sReceivePortName];  
  
foreach(ReceiveLocation rl in rp.ReceiveLocations)  
rl.Enable = false;  
  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
private bool StartOrchestration(string sOrchestrationName)  
{  
  
BtsAssemblyCollection btsAssemblyCollection = bceExplorer.Assemblies;  
  
foreach (Microsoft.BizTalk.ExplorerOM.BtsAssembly btsAssembly in btsAssemblyCollection)  
{  
if(sOrchestrationName.Split(',')[1]==btsAssembly.DisplayName.Split(',')[0])  
{  
foreach (Microsoft.BizTalk.ExplorerOM.BtsOrchestration btsOrchestration in btsAssembly.Orchestrations)  
{  
if(sOrchestrationName==btsOrchestration.AssemblyQualifiedName)  
{  
btsOrchestration.Status=OrchestrationStatus.Started;  
try  
{  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
}  
}  
}  
return false;  
}  
  
private bool UnenlistOrchestration(string sOrchestrationName)  
{  
  
BtsAssemblyCollection btsAssemblyCollection = bceExplorer.Assemblies;  
  
foreach (Microsoft.BizTalk.ExplorerOM.BtsAssembly btsAssembly in btsAssemblyCollection)  
{  
if(sOrchestrationName.Split(',')[1]==btsAssembly.DisplayName.Split(',')[0])  
{  
foreach (Microsoft.BizTalk.ExplorerOM.BtsOrchestration btsOrchestration in btsAssembly.Orchestrations)  
{  
if(sOrchestrationName==btsOrchestration.AssemblyQualifiedName)  
{  
btsOrchestration.AutoTerminateInstances=true;  
btsOrchestration.Status=OrchestrationStatus.Unenlisted;  
try  
{  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
}  
}  
}  
return false;  
}  
  
}  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1bda-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f1bda-122">See Also</span></span>  
 [<span data-ttu-id="f1bda-123">示例</span><span class="sxs-lookup"><span data-stu-id="f1bda-123">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)