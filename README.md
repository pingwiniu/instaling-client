# Instaling Client

[![PyPI version](https://img.shields.io/pypi/v/instaling-client.svg)](https://pypi.org/project/instaling-client/)
[![PyPI Downloads](https://static.pepy.tech/badge/instaling-client/week)](https://pepy.tech/projects/instaling-client)
[![License: GPL v2](https://img.shields.io/badge/License-GPL_v2-blue.svg)](https://www.gnu.org/licenses/old-licenses/gpl-2.0.en.html)

A Python client for automating Instaling language learning sessions. This package provides a convenient way to interact with the Instaling platform programmatically.
It is much faster than instaling-solver since the basis of it is the API of the website itself, not a selenium instance.

## Installation

Install the package using pip:

```bash
pip install instaling-client
```

## Examples

### Complete Daily Session

```python
from instaling_client import InstalingClient

client = InstalingClient()
try:
    client.login("username", "password")
    
    if client.session_completed:
        print("Today's session is already completed!")
    else:
        print("Starting today's session...")
        client.solve_quiz()
        print("Session completed successfully!")
        
except ValueError as e:
    print(f"Authentication error: {e}")
except requests.exceptions.HTTPError as e:
    print(f"HTTP error: {e}")
```

## License

This project is licensed under the GNU General Public License v2 (GPLv2) - see the [LICENSE](LICENSE) file for details.

## Disclaimer

This tool is for educational purposes only. Using automation tools may violate Instaling's terms of service. Use at your own risk and responsibility.
The creators and maintainers of this package are not affiliated with, endorsed by, or connected to Instaling.pl or its parent company. This is an unofficial client implementation. 
