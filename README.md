# EpicGames-Bypass
# How to use
```
$ "-epicapp=Fortnite -epicenv=Prod -epiclocale=en-us -epicportal -noeac -fromfl=be fltoken=YOURTOKEN" + extraArgs
$ Just add this to your DLL or launcher :)
```
EXAMPLE:
```
	public static Process StartProcess(string path, bool shouldFreeze, string extraArgs = "")
		{
			Process process = new Process
			{
				StartInfo = new ProcessStartInfo
				{
					FileName = path,
					Arguments = "-epicapp=Fortnite -epicenv=Prod -epiclocale=en-us -epicportal -noeac -fromfl=be -fltoken=EXAMPLETOKEN2f23 " + extraArgs
				}
			};
			process.Start();
			if (shouldFreeze)
			{
				foreach (object obj in process.Threads)
				{
					ProcessThread processThread = (ProcessThread)obj;
					ProcessHelper.SuspendThread(ProcessHelper.OpenThread(2, false, processThread.Id));
				}
			}
			return process;
		}
```
