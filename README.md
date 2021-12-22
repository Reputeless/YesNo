# siv::YesNo

## Usage
```cpp
# include <iostream>
# include "YesNo.hpp"

using siv::YesNo;
using FormatDisk = YesNo<struct FormatDisk_tag>;
using WriteLog = YesNo<struct WriteLog_tag>;

void Task(FormatDisk formaDisk, WriteLog writeLog)
{
	if (formaDisk)
		std::cout << "Formatting a disk...\n";
	if (writeLog)
		std::cout << "Writing a log...\n";
}

int main()
{
	Task(FormatDisk::No, WriteLog::Yes);
	Task(FormatDisk{ false }, WriteLog{ true });

	Task(WriteLog::Yes, FormatDisk::No); // error
	Task(false, true); // error
}
```

## License
siv::YesNo is distributed under the **Boost Software License 1.0**.
