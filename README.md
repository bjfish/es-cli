## es-cli

A command line interface for elasticsearch

    COMMANDS
        cluster health [profile]  - Print the cluster health
        c h [profile]             - Same as cluster health


### Installation

`gem install es-cli`

#### Optional - add an alias to your `.bash_profile`

`alias es='es-cli'`


### Configuration File for Profiles

Example `.es-cli.yml` which goes in your home directory.

<pre>
    ---
    # The default profile that will activate by default when no parameter is given
    :default:
      :es_url: http://localhost:9200
    # Add `stage` to end of command to use stage profile
    :stage:
      :es_url: http://localhost:9300

</pre>

Run a command with a profile activated:

`es-cli -p stage cluster health`

### Example Commands

Example `cluster health` command:


    $es-cli c h
    {
                   "cluster_name" => "elasticsearch",
                         "status" => "green",
                      "timed_out" => false,
                "number_of_nodes" => 1,
           "number_of_data_nodes" => 1,
          "active_primary_shards" => 0,
                  "active_shards" => 0,
              "relocating_shards" => 0,
            "initializing_shards" => 0,
              "unassigned_shards" => 0,
        "number_of_pending_tasks" => 0
    }

Example `node stats` command:


    $es-cli node stats --m transport
    {
        "cluster_name" => "elasticsearch",
               "nodes" => {
            "E4MVBLgxRoqvETui00Y3GA" => {
                        "timestamp" => 1431057233915,
                             "name" => "Mindworm",
                "transport_address" => "inet[/10.0.0.10:9300]",
                             "host" => "Brandons-MacBook-Pro.local",
                               "ip" => [
                    [0] "inet[/10.0.0.10:9300]",
                    [1] "NONE"
                ],
                        "transport" => {
                         "server_open" => 13,
                            "rx_count" => 6,
                    "rx_size_in_bytes" => 1584,
                            "tx_count" => 6,
                    "tx_size_in_bytes" => 1584
                }
            }
        }
    }


### TODO
- add more commands
- add more options
- add global settings

