# siv::YesNo

## Usage
```cpp
# include <iostream>
# include "YesNo.hpp"

using siv::YesNo;
using FormatDisk = YesNo<struct FormatDisk_tag>;
using WriteLog = YesNo<struct WriteLog_tag>;

void DoTask(FormatDisk formaDisk, WriteLog writeLog)
{
	if (formaDisk)
		std::cout << "Formatting a disk...\n";
	if (writeLog)
		std::cout << "Writing a log...\n";
}

int main()
{
	DoTask(FormatDisk::No, WriteLog::Yes);
	DoTask(FormatDisk{ false }, WriteLog{ true });

	DoTask(WriteLog::Yes, FormatDisk::No); // error
	DoTask(false, true); // error
}
```

## License
siv::YesNo is distributed under the **Boost Software License 1.0**.
