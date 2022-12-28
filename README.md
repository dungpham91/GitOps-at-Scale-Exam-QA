# GitOps-at-Scale-Exam-QA
Summary of questions and answers when doing Codefresh's GitOps at Scale test.

1. `An Argo CD hook that runs in the PreSync phase has an error and fails. Argo CD will` -> Abort the deployment

2. `Resource A is in the PreSync phase with Sync wave 50. Resource B is in the SyncFail phase with Sync Wave  -50. Resource C is in the PostSync phase with wave -99` -> 
Resource A will be deployed first, then Resource B (if applicable). Resource C will be deployed last

3. `If a hook in the PostSync phase has an error, Argo CD` -> will abort the deployment and mark it as failed

4. `When do you need to ignore differences in Argo CD resources?` -> When an application has values that should be dynamically modified after manifests are applied.

5. `An application has a “deny” sync window for 5pm to 8pm and an “allow” sync window from 6pm to 9pm. The time is now 7pm` -> You cannot deploy the application, “deny” windows override “allow” windows

6. `An application has an “allow” sync window for 5pm to 6pm. The time is now 7pm` -> You can deploy the application as no sync window is active

7. `What is the best way according to the GitOps principles to update the container of an application` -> Use Argo Image updater and the “Argo CD write back” method

8. `Resource A is in the PreSync phase with Sync wave 50. Resource B is in the Sync phase with Sync Wave  -10. Resource C is in the PostSync phase with wave 50` -> Resource A will be deployed first then Resource B and finally Resource C

9. `What is the major disadvantage of using branches as GitOps environments?` -> Order of commits affects every promotion done by merging

10. `Argo CD will mark an application as Failed if...` -> Any hook fails regardless of its phase

11. `An application has a “deny” sync window for 5pm to 7 pm, an “allow” sync window from 4pm to 8pm. The time is now 6pm` -> You cannot deploy the application, “deny” windows override “allow” windows

12. `What is the relationship between Application Sets and Apps of Apps?` -> Both approaches are independent of each other

13. `An application has a “deny” sync window for 5pm to 6pm. The time is now 7pm` -> You can deploy the application because no “deny” window is active

14. `Can you use Application Sets with App of Apps applications?` -> Yes, they can be combined but only if the controllers are the same version

15. `You have lots of applications in a single Git repository under “/infra/apps/<app-name>”. The correct ApplicationSet generator to use is` -> Git Generator

16. `What is the relationship between Sync Waves and phases?` -> Sync waves and phases can be used on their own or both at once

17. `What is the major disadvantage of disabling “self-heal” in an application` -> Manual changes in the cluster will no longer be detected and discarded

18. `How can you model different GitOps environments?` -> Any of the above

19. `How do Application Sets work?` -> Application Sets are generators for Argo CD applications

20. `If you define “self-heal” for a root application that contains other applications...` -> Self-heal is enabled for both parent and child apps

21. `How can you combine Application Set Generators?` -> By using a matrix generator

22. `What is the major advantage of using folders as GitOps environments?` -> All the above

23. `How can you use the Apps of Apps pattern?` -> All of the above

24. `Resource A is marked with Sync Wave -1 and placed in the Presync phase. Resource B is marked with Sync Wave: -99 and placed in the Skip phase` -> None of the above

25. `It's possible to add an external cluster to Argo CD…` -> Using the CLI

26. `How does Argo Image Updater work?` -> It monitors Docker registries for new containers

27. `Resource A is in the PreSync phase and Sync wave 10. Resource B is in the Sync phase and has Sync wave 20. Resource C is in the SyncFail phase with sync wave 30` -> C will be deployed only if B fails to deploy

28. `If a hook in the SyncFail phase has an error, Argo CD` -> will abort the deployment and mark it as failed

29. `What is the major advantage of using branches as GitOps environments?` -> Developers are already familiar with how git tools work

30. `For what scenarios can you use Application Sets?` -> All of the above

31. `How does the Apps of Apps pattern work?` -> You create an Argo CD application that points to other applications

32. `What is the best way of modeling your GitOps environments?` -> Using folders in a single git repository

33. `What are Sync Windows used for?` -> To disable/enable application deployments for different time periods

34. `You have a production environment that gets container images with tags that match only 1.x version. The appropriate Argo Image updater strategy is` -> semver

35. `You have an application managed by Argo Image Updater with the “semver” strategy. The current image is tagged “1.4” with a constraint to “1.x” releases. You build a new image and push it with tag 1.2.7. This new container` -> will not be deployed because 1.4 is newer

36. `Where should you deploy an Argo CD application manifest?` -> In the “argo” namespace

37. `When you add an external cluster in Argo CD…` -> You need a context for the target cluster and the CLI authenticated to the management cluster

38. `Resource A is marked with Sync wave -1 and Resource B is marked with wave 5.` -> We need to check for sync phases before we can answer

39. `Resource A is in the PostSync phase and has Sync wave 5. Resource B is in the PostSync phase and has Sync Wave 5. Resource C is in the PostSync phase and has Sync Wave -10` -> C will be deployed first and then A and B will be deployed according to default Resource order

40. `What is the Apps of Apps pattern?` -> A way to group multiple Argo CD applications together

41. `When you add an external/target cluster in Argo CD...` -> The management cluster needs network access to the target cluster

42. `Can you use sync waves to replace sync phases?` -> Yes, but only if you don’t need the SyncFail mechanism

43. `You want an Argo CD application to be deployed as soon as somebody creates a new Github repository with manifests. Which ApplicationSet generator should be used?` -> SCM provider Generator

44. `Resource A is in the Sync phase and has no Sync wave. Resource B is in the Sync phase and has Sync wave 0` -> A and B will be deployed according to the default Resource ordering

45. `What is the major disadvantage of using folders as GitOps environments?` -> It is difficult to secure individual folders in a single git repository

46. `You have a “staging” container tag that should always be deployed to a staging environment as soon as somebody updates it. The appropriate Argo Image updater strategy is` -> latest

47. `An application has a “deny” sync window for 5pm to 7 pm, an “allow” sync window from 4pm to 7pm and an “allow” window from 5:30 to 6:30pm. The time is now 6pm` -> You cannot deploy the application, “deny” windows override “allow” windows

48. `What source can be used for Application Sets?` -> All of the above

49. `How does Argo CD manage Kubernetes clusters?` -> All of the above are valid scenarios

50. `You want to create temporary environments for developers while they create new features on different branches. The correct ApplicationSet generator to use is` -> Pull Request Generator
